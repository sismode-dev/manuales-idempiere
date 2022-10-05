# Autoasignación de usuario, localización y precios para una orden de venta

Las ordenes de venta provienen de un sistema externo al ERP de Sismode, en este caso son enviadas a través de una empresa llamada BDO ADVIRSOR
hacia el ERP de IDEMPIERE; a las ordenes de venta se le asigna la dirección del usuario envase al RUC del encabezado de la orden,
esto lo hacen buscandolo en la localización del contacto del cliente BDO.

![idempiere](./img/id.jpg)

## _**Entidades Participantes**_

- **tercero** (cliente) es con quién se realiza transacciones, en este caso el tercero BDO. 
- **La orden** es la que proviene del sistema externo de BDO.

- **Localización** es un campo clave dentro de la orden que debe ser actualizado envase al RUC.
- **ISDN** es el campo que está dentro de la localización, en este campo se debe colocar el RUC.

- **Contácto (*usuario*)** es un campo clave dentro de la orden de venta, que se actualiza y se toman desde el tercero BDO considerando al RUC.
- **Línea de orden** es donde se ubican los productos y estas lineas van hacer actualizadas envase al precio.
- **Producto** puede ser comprado o vendido.


