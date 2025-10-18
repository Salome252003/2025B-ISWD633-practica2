## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR

docker network create net-wp -d bridge

<img width="790" height="43" alt="image" src="https://github.com/user-attachments/assets/d7bd0748-530b-43ec-8424-2b856c3fa30b" />


### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR

docker run -d --name contenedor-mysql --network net-wp -e MYSQL_ROOT_PASSWORD=salome123 -e MYSQL_DATABASE=wordpressdb -e MYSQL_USER=priscila -e MYSQL_PASSWORD=salome123 mysql:8

<img width="1755" height="371" alt="image" src="https://github.com/user-attachments/assets/0f89b4a3-47d4-46ea-a358-cadb6279aa1e" />

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR

docker run -d --name contenedor-wordpress --network net-wp -e WORDPRESS_DB_HOST=contenedor-mysql:3306 -e WORDPRESS_DB_USER=priscila -e WORDPRESS_DB_PASSWORD=salome123 -e WORDPRESS_DB_NAME=wordpressdb -p 8080:80 wordpress

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **8080**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN

<img width="1917" height="956" alt="image" src="https://github.com/user-attachments/assets/5e851b40-5300-4ae5-9189-e8d7a5a895a9" />

<img width="1918" height="961" alt="image" src="https://github.com/user-attachments/assets/1766d52d-3365-4ad7-b46f-948e471f0bfd" />


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.

<img width="1906" height="957" alt="image" src="https://github.com/user-attachments/assets/41b39ba0-f5f8-46fe-a653-f878df66f78a" />

### Eliminar el contenedor wordpress
# COMPLETAR

docker rm -f contenedor-wordpress

<img width="667" height="51" alt="image" src="https://github.com/user-attachments/assets/e9372838-9440-4876-81e3-929b46d13e70" />


### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR

El sitio web se mantiene con la configuración y la publucación recientemente creado y esto ocurre porque la información se almacena en la base de datos MySQL
