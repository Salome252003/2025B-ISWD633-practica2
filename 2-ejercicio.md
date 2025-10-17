### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21

# COMPLETAR

docker run -d --name contenedorPostgres --network red-postgres -e POSTGRES_USER=priscila -e POSTGRES_PASSWORD=salome123 -e POSTGRES_DB=info postgres:15-alpine3.21

<img width="1457" height="71" alt="image" src="https://github.com/user-attachments/assets/28177815-7390-4ef1-97a6-6a9452dd13a7" />

### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4

docker run -d --name clientePostgres --network red-postgres -e PGADMIN_DEFAULT_EMAIL=priscila@salome.com -e PGADMIN_DEFAULT_PASSWORD=salome123 -p 8081:80 dpage/pgadmin4

<img width="1457" height="70" alt="image" src="https://github.com/user-attachments/assets/80b5302e-7a62-459f-aa34-15a2db4f2ba2" />


# COMPLETAR

La figura presenta el esquema creado en donde los puertos son:
- a: (8081:80)
- b: (5432)
- c: (5432)

<img width="1462" height="162" alt="image" src="https://github.com/user-attachments/assets/b921cfb7-4ac6-4e8f-a414-a5ea9484c97a" />


![Imagen](esquema-2-ejercicio.PNG)

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN

PSe debe entrar a la pagina: http://localhost:8081/

Email: priscila@salome.com

Password: salome123

<img width="1918" height="1025" alt="image" src="https://github.com/user-attachments/assets/a5926a9c-19c1-47dd-9562-c54e82a49f01" />

<img width="1918" height="1027" alt="image" src="https://github.com/user-attachments/assets/10e62b14-1c49-4942-9dfd-dd63a0ec983d" />


### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

## Desde el servidor postgresl
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR

<img width="1912" height="852" alt="image" src="https://github.com/user-attachments/assets/db175c4f-f7ca-4bb2-b976-8978f605d2d9" />

##Para la creación de la tabla Persona

CREATE TABLE personas (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100)
);

INSERT INTO personas (nombre) VALUES
('Priscila Pazmiño'),
('Carlos Pérez');

SELECT * FROM personas;;


### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO

<img width="1916" height="867" alt="image" src="https://github.com/user-attachments/assets/6a8cada4-4abc-4d42-b7df-199d61017847" />
