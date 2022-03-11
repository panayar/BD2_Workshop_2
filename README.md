# Taller 2 BD 
## Diagrama Relacional 
https://lucid.app/lucidchart/e761f93f-5de6-4371-8960-5493da2203dd/edit?invitationId=inv_348e8025-6a6c-4bf0-a55d-fc39744f3e7a

## Registro de auditoría de las tablas de producto y variante.

```create table Compra_detalle(
    producto_compra_id serial not null ,
    producto_id int not null ,
    compra_id int not null ,
    cantidad int,
    precio_unidad float,
    estado boolean,
    primary key (producto_compra_id),
    foreign key (producto_id) references Producto(producto_id),
    foreign key (compra_id) references Compra(compra_id)
);
create table Carrito_detalle(
    carrito_det_id serial not null ,
    carrito_id int not null ,
    producto_id int not null ,
    cantidad int,
    estado boolean,
    primary key (carrito_det_id),
    foreign key (carrito_id) references Carrito (carrito_id),
    foreign key (producto_id) references Producto (producto_id)
);
create table variante(
    variante_id serial not null ,
    producto_id int not null ,
    descripcion varchar(200),
    stock bigint,
    estado boolean,
    primary key (variante_id),
    foreign key (producto_id) references Producto (producto_id)
);
create table Product_audit(
    producto_id serial not null ,
    marca varchar(100) ,
    proveedor varchar(100) ,
    categoria varchar(90),
    event_type varchar(100),
    event_datetime date,
    titulo varchar(80),
    precio float,
    caracteristicas varchar(100),
    descripcion varchar(100),
    estado boolean,
    primary key (producto_id)
);
create table Variant_audit(
    variante_id serial not null ,
    producto varchar(100) ,
    descripcion varchar(200),
    caracteristicas varchar(100),
    marca varchar(100) ,
    event_type varchar(100),
    event_datetime date,
    stock bigint,
    estado boolean,
    primary key (variante_id)
);
create table Producto_Historico(
    producto_id serial not null ,
    marca_id int not null ,
    proveedor_id int not null ,
    titulo varchar(100),
    variante varchar(100),
    precio float,
    caracteristicas varchar(100),
    primary key (producto_id),
    foreign key (marca_id) references Marca (marca_id),
    foreign key (proveedor_id) references Proveedor (proveedor_id)
);
create table weekly_reputation(
    weekly_id serial not null ,
    producto_id int not null ,
    compador_id int not null ,
    calificacion float ,
    comentario varchar(150),
```
## Integrantes 👧🏻🦸‍♂️👨‍🚀
* Paula Andrea Anaya Ramirez
* Luis Esteban Cardenas Cortes
* Cristian David Sanchez Malagon
