# Autoasignación de usuario, localización y precios para una orden de venta

Las ordenes de venta provienen de un sistema externo al ERP de Sismode, en este caso son enviadas a través de una empresa llamada BDO ADVIRSOR
hacia el ERP de IDEMPIERE; a las ordenes de venta se le asigna la direcciÓn del usuario envase al RUC del encabezado de la orden,
esto lo hacen buscandolo en la localización del contacto del cliente BDO.

![idempiere](./img/id.jpg)

## _**Entidades Participantes**_

- **El tercero** es con quién se realiza transacciones, en este caso el tercero BDO. 
- **La orden** es la que proviene del sistema externo de BDO.

- **Localización** es un campo clave dentro de la orden que debe ser actualizado envase al RUC.
- **ISDN** es el campo que está dentro de la localización .

- **Contácto (*usuario*)** es un campo clave dentro de la orden de venta, que se actualiza y se toman desde el tercero BDO considerando al RUC.
- **Línea de orden** es donde se ubican los productos y estas lineas van hacer actualizadas envase al precio.
- **Producto** puede ser comprado o vendido.

# Configuraciones necesarias para este desarrollo

## _**Primera Configuración**_

 En la lista de precios se pueden manejar varias listas en donde se determina la moneda del documento así como el tratamiento de impuestos.

 Hay varias formas de crear un listado de precios, a continuación se le explica la primera:
 
 Siga los siguientes pasos:
 
  1. Digite la palabra __*lista de precio*__ en el menú de búsqueda principal.
  2. Ubique la lista de precioso BDO, en caso de no existir cree la lista de precios de BDO.

  3. Descienda a la versión de lista de precio. 
  4. En el __*Esquema lista de precios*__ seleccione *BDO*. 

  5. Asegurese de colocar una fecha que no este repetida, a fin de que el sistema le deje guardar los cambios deseados.  
  6. Baje a la pestaña de productos. 

  7. Digite el precio de productos.
  8. Digite el precio de lista.

  9. Digite el precio estándar
  10. Digite el precio lÍmite.

  11. Configuración del RUC dentro de la localización en el campo ISR.
  12. Coloque el campo del RUC dentro del Usuario.

## _**Configuraciones del Sistema**_

Dentro de está configuración se puede cambiar valores que esten actualmente configurados un claro ejemplo sería a qué usuario se le va a enviar el correo, cuál es la localización
o el usuario por defecto esto sería en el caso de que un futuro varie el ID de BDO lo podrían cambiar.

También se podrá observar si se habilita o deshabilita el desarrollo actual. 

Para realizar dicha configuración, se realiza los siguientes pasos:

1. Configuración BDO_AUTOMATIC_ASSIGNMENT_ENABLED
Habilita la autoasignación de usuarios, direcciones y precios para las ordenes de venta de BDO.
 
2.  Configuración BDO_BP_ID 
id_BDO en la ventana de terceros en caso de que varie el ID del BDO se puede actualizar.

3. Configuración BDO_DEFAULT_LOCATION_ID
El id de ubicación por defecto para direcciones del tercero relacionado de BDO (en caso de no encontrar la correcta).

4. Configuración BDO_DEFAULT_USER_ID
El id de usuario por defecto de caso de no poder asociar un contacto a través del RUC del relacionado.

5. Configuración BDO_MAIL_TEXT_TO_ALERT
El texto de notificación de nueva orden de venta de BDO.

6. Configuración BDO_USER_ID_TO_ALERT
El id del usuario a quien se le envía los correos electrónicos de asignación de usuario y localización de ordenes BDO.

