# Actividad Factura - Parcial Segundo Corte

1.	Para empezar vamos abrir  el archivo con las instrucciones para la creación de nuestros triggers 
2.	Seleccionamos la instrucción y la ejecutamos, recordemos que la instrucción la podemos ejecutar presionando la tecla F5  o haciendo clic en el botón Execute
3.	y vemos que a cada instrucción que ejecutamos dentro de la interfaz el manejador nos responde haciéndonos saber el status de ejecución de la instrucción 
4.	Para probar nuestro trigger lo primero que vamos hacer es crear una tabla de facturas y una tabla de detalles vamos a incluir pocos campos solamente numero de la factura  un código de cliente ,la fecha y el total de la  factura que vamos a poner un valor por defecto de 0 y a la tabla de detalles le vamos agregar el código de la factura como llave foránea con la tablas facturas un entero para identificar un  número  de detalle un producto cualquiera que va hacer un dato nada más descriptivo y el total de ese detalle .
5.	Podemos ejecutar las dos instrucciones a la vez ,la seleccionamos y probamos f5 y el manejador nos responde que los comandos fueron ejecutados sin ningún problema
6.	Ahora vamos a la izquierda al explorador de objectos ,abrir la carpeta de las bases de datos, la base de datos temporal esta adentro de la base de datos del sistema y si abrimos la base de datos temporal ,dentro de la carpeta correspondiente a las tablas, vamos a tener nuestras dos tablas que acabamos de crear, facturas y facturas detalles.
Cada una de estas tablas tiene metadata,y una de las carpetas correspondientes a la metadata es la carpeta de los triggers ,miramos que en este caso la carpeta esta vacia.
7.	Volviendo a nuestro script vamos a proceder a la creación de nuestro trigger, para crear el trigger simplemente seleccionamos la instrucción y la ejecutamos presionando f5, de nuevo obtenemos el mensaje de que el comando pudo ser ejecutado sin ningún problema y si vinimos a nuestra carpeta de triggers, le damos botón derecho, refrescar. Ahí va aparecer nuestro trigger que acabamos de crear.
8.	Vamos a verificar que el trigger funciona para esto, vamos primero a ver que nuestras tablas de factura y detalles, están vacías.
9.	Y luego vamos a crear dos facturas la factura 1, para el cliente 10 y la factura 2 para el cliente 15,si nos fijamos bien  no estamos insertando el total de las facturas porque al definir la factura el campo total dijimos que iba a tener un valor por defecto de 0,veamos que cada vez que ejecutamos una instrucción que afecta una tabla ,el manejador me responde con la cantidad de filas que fueron afectadas, en este caso insertamos dos facturas y el manejador nos dice que se afectaron dos filas .
10.	Y estas son las dos facturas que acabamos de crear 
11.	Vamos ahora a crear un detalle en la factura 1,en la factura 1 en el detalle 1,vamos a crear un detalle con un total de 100,y en este caso lo que estamos esperando es que  el total de la factura 1,también sea 100.
12.	Insertamos el detalle ,lo primero que hay que notar fue que insertamos un solo detalle,sin embargo el manejador nos esta diciendo que se afectaron dos filas 
13.	Esta primera fila es la afectación del trigger a la tabla de facturas

14.	Y después de que se ejecuto el trigger ,entonces se inserto la fila en la tabla de detalles 
15.	Vamos a verificar nuestras dos tablas ,la tabla de facturas y la tabla de detalles, en este caso la factura numero 1 ,tiene un total de 100,que es la suma de los detalles de la factura 1, automáticamente el trigger ha afectado del total de la factura.
16.	Vamos a crear multiplex detalles en la misma factura, insertemos 3 detalles en la factura numero 2.la suma de esos 3 detalles es 150.
Por lo tanto, esperamos que el nuevo total de nuestra factura 2, sea 150.hagamos la inserción dentro de la misma transacción 
17.	primero  se nos dice que se afecto una fila la fila de la factura y luego se afectaron  3 nuevas filas, que fueron los 3 detalles que se acabaron de insertar.
18.	vamos a verificar de nuevo nuestras tablas de facturas y nuestras tablas de detalles y podemos ver abajo los 3 detalles y la factura 2 fue afectada y se le coloco un total de 150. Podemos ver que nuestro trigger está funcionando.
19.	vamos a crear ahora detalles en diferentes facturas, en este caso vamos a crear dos detalles en la factura 1, y un detalle en la factura 2, la factura 1 que actualmente tiene un total de 100, le vamos agregar un detalle de 150, y uno de 25, y a la factura 2 que tiene un total de 150, le vamos agregar un detalle con un total de 10.
