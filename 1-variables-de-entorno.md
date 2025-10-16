# Variables de Entorno
### ¿Qué son las variables de entorno?
# COMPLETAR
Son datos que el sistema o un contenedor necesita para funcionar correctamente, sin tener que escribir esa información directamente dentro del código.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETAR
docker run -d --name srv-web6 -e username="usuario1" -e role="admin" nginx:alpine

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR

<img width="1221" height="42" alt="image" src="https://github.com/user-attachments/assets/f7e55b74-3d14-41e9-a8e3-24baa0e044a1" />


### Crear un contenedor con la imagen de mysql, mapear todos los puertos
docker run -d --name contenedorMySQL -e MYSQL_ROOT_PASSWORD="admin123" -p 3307:3306 mysql:latest

<img width="1060" height="273" alt="image" src="https://github.com/user-attachments/assets/c1956927-b253-4ff7-b727-23d3438059a5" />
-----------------------------------------------------------------------------------------------------------------------------------------

<img width="886" height="33" alt="image" src="https://github.com/user-attachments/assets/e58ef174-f8d1-467e-97cb-4040585ae37b" />

# COMPLETAR

### ¿El contenedor se está ejecutando?
# COMPLETAR

Si el contenedor MySQL se está ejecutando usando la imagen mysql:latest y tiene mapeado el puerto 3307 del host al puerto 3306 del contenedor.

<img width="1452" height="127" alt="image" src="https://github.com/user-attachments/assets/955a52f9-d1f0-4be1-913b-93671c2d2e0e" />

### Identificar el problema
# COMPLETAR
Al intentar crear el contenedor de MySQL, se presentaron dos problemas principales los nombres y los puertos. 

Soluciones 
- Se usó otro nombre
- Se reasignó el puerto a 3307:3306, permitiendo la correcta ejecución del nuevo contenedor



### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
docker exec -it contenedorMySQL mysql -u root -p

password: admin123


Una vez dentro del contenedor, se coloca el siguiente comando:

SHOW DATABASES;

<img width="947" height="562" alt="image" src="https://github.com/user-attachments/assets/91c3f9ff-b1c1-4fd7-8bca-f79b4bdc6405" />

Por lo tanto, las bases de datos que hay son: 

-information_schema

-mysql

-performance_schema

-sys


