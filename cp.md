# 4.- Casos prácticos.

## a) Versión de Nginx instalado.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/version.png)

## b) Ficheros de configuración.

## c) Página web por defecto.

Modifica la página web que lanza por defecto y personalízala.

## d) Virtual Hosting.
Queremos que nuestro servidor web ofrezca balanceo de carga desde https  a dos sitios web que tengan también https.

Instalamos un certificado para nuestra web con openssl.

Añadimos los archivos a la configuración de nginx.

Comprobamos.

Redirigimos nuestro servidor nginx al puerto 8081 para darle el 443 al balanceador.

Añadimos la configuración del balanceador a la de nginx. Estará en la ip 192.168.1.58.
Ponemos ip y puerto para dirigirse correctamente a cada server del balanceador.
Configuramos el server del puerto 80 para que todas las peticiones http se redirijan a https.
Configuramos el balanceador en el puerto 443 con su configuración para ssl.
El el proxy_pass pondremos https://myproject para que abra como https los servidores. 

En el navegador comprobamos el balanceo entre nginx en ip 58 y apache en ip 57.

