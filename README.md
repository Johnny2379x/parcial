--integrantes 
--Carrasco Chinchay Henry Eli
--Huamani Calle Kevin Johnny
--Mercado Cornejo Favio Armando



CREATE TABLE empleado(
    IDEmpleado       NUMBER PRIMARY KEY,
    NombreEmpleado    VARCHAR2(20) NOT NULL,
    ApellidoEmpleado    VARCHAR2(50) NOT NULL,
    DNI         CHAR(8) NOT NULL UNIQUE,
    SexoEmpleado        VARCHAR2(20),
    DireccionEmpleado   VARCHAR2(20),
    TelefonoEmpleado    VARCHAR2(10),
    ClaveEmpleado       VARCHAR2(20),    
    CodigoTipoEmpleado   NUMBER REFERENCES tipo_cliente
   
);
COMMIT;


CREATE TABLE venta(
    IDVenta          NUMBER PRIMARY KEY,
    FechaVenta       DATE,
    TotalVenta       VARCHAR2(20),
    CodigoEmpleado   VARCHAR2(20),
    NumeroCliente    NUMBER REFERENCES cliente
);
COMMIT;

CREATE TABLE cliente(
    IDCliente          NUMBER PRIMARY KEY,
    NombreCliente      VARCHAR2(50) NOT NULL,
    ApellidoCliente    VARCHAR2(50) NOT NULL,
    DNI                CHAR(8) NOT NULL UNIQUE,
    SexoCliente        VARCHAR2(10),
    DireccionCliente   VARCHAR2(20),
    TelefonoCliente    VARCHAR2(10),
    CodigoTipoCliente  NUMBER REFERENCES tipo_cliente
   
);
COMMIT;

CREATE TABLE comida(
    IDComida             NUMBER PRIMARY KEY,
    NombreComida         VARCHAR2(20) NOT NULL,
    DescripcionComida    VARCHAR2(20),
    PrecioComida         VARCHAR2(10),
    CodigoTipoComida     NUMBER REFERENCES tipo_comida
);
COMMIT;

CREATE TABLE tipo_empleado(
    IDTipoEmpleado        NUMBER PRIMARY KEY,
    NombreTipoEmpleado    VARCHAR2(20) NOT NULL
);

CREATE TABLE tipo_cliente(
    IDTipoCliente        NUMBER PRIMARY KEY,
    NombreTipoCliente    VARCHAR2(20) NOT NULL
);

CREATE TABLE tipo_comida(
    IDTipoComida        NUMBER PRIMARY KEY,
    NombreTipoComida    VARCHAR2(20) NOT NULL
);
