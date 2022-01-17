# 4.- Casos prácticos.

## a) Versión de Nginx instalado.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/version.png)

## b) Ficheros de configuración.
Los sitios virtuales de nginx estan en /etc/nginx/sites-available/
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/configuracion.png)

## c) Página web por defecto.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_defecto.png)

![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_defecto1.png)

Modifica la página web que lanza por defecto y personalízala.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_mod.png)

![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_mod1.png)

## d) Virtual Hosting.
Queremos que nuestro servidor web ofrezca balanceo de carga desde https  a dos sitios web que tengan también https.

Instalamos un certificado para nuestra web con openssl.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/openssl.png)

Añadimos los archivos a la configuración de nginx.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/default_ssl.png)

Comprobamos.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_ssl.png)

![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_ssl1.png)

Redirigimos nuestro servidor nginx al puerto 8081 para darle el 443 al balanceador.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/default_8081.png)

![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_8081.png)

Añadimos la configuración del balanceador a la de nginx que estará en la ip 192.168.1.58.
Ponemos ip y puerto para dirigirse correctamente a cada server del balanceador.
Configuramos el server del puerto 80 para que todas las peticiones http se redirijan a https.
Configuramos el balanceador en el puerto 443 con su configuración para ssl.
El el proxy_pass pondremos https://myproject para que abra como https los servidores. 
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/default_bal.png)

En el navegador comprobamos el balanceo entre nginx en ip 58 y apache en ip 57.
![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_bal.png)

![imagen](https://github.com/mikkgh/nginx/blob/main/imagenes/web_bal1.png)

