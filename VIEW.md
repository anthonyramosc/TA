###  1. Crear una vista que muestre la lista de productos comprados por los clientes con las siguientes columnas: 
**Base de datos: invoice nombre_cliente | fecha_compra | nombre_producto | cantidad**

````
CREATE VIEW productos_comprados AS
SELECT 
    c.fullname AS nombre_cliente,
    i.create_at AS fecha_compra,
    p.description AS nombre_producto,
    d.quantiy AS cantidad
FROM 
    Client c
JOIN 
    Invoice i ON c.id = i.id_client
JOIN 
    Detail d ON i.id = d.id_invoice
JOIN 
    Product p ON d.product_id = p.id;

````
![[40.png]]
![[41.png]]

###  2. Crear una vista donde se muestre la lista de miembros registrados a las conferencias.

**Base de datos: event nombre_conferencia | codigo_registro | nombre_miembro**

````
CREATE VIEW members AS
SELECT 
    c.title AS nombre_conferencia,
    r.code AS codigo_registro,
    m.fullname AS nombre_miembro
FROM 
    conference c
JOIN 
    register r ON c.id = r.id_conference
JOIN 
    member m ON r.member_id = m.id;
````
![[42.png]]

![[43.png]]