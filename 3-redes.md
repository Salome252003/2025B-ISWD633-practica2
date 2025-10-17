# Redes
Las redes son un componente fundamental que permite la comunicación entre contenedores, así como la comunicación de los contenedores con el mundo exterior. 
![Imagen](redes.PNG)
- Bridge: Esta es la red por defecto en Docker. Permite la comunicación entre contenedores en el mismo host. Cada contenedor conectado a la red bridge tiene una IP propia en la subred de la red bridge.
    -  Brige por default: Cuando se ejecuta un contenedor, Docker crea automáticamente una red de tipo bridge por default. Esta red se utiliza para permitir la comunicación entre contenedores en el mismo host. Cada contenedor conectado a esta red obtiene su propia dirección IP en la subred de la red bridge.
    - Bridge creada por nosotros: Un usuario también puede crear sus propias redes de tipo bridge en Docker. Esto puede ser útil para organizar y segmentar los contenedores de una aplicación de manera más controlada. Al crear una red bridge personalizada, se puede especificar un rango de direcciones IP y otras configuraciones de red específicas. Los contenedores conectados a esta red utilizarán las direcciones IP de la subred definida por el usuario.
- Host: Con esta red, los contenedores comparten la red del host en lugar de tener su propia interfaz de red. Esto puede mejorar el rendimiento de red, pero los contenedores pueden entrar en conflicto con los puertos del host si intentan utilizar los mismos puertos.
- None: Con esta red, se deshabilita la configuración de red. Los contenedores que usan esta red tienen su propia red de loopback y no pueden comunicarse con otros contenedores a menos que se conecten explícitamente a una red.

### Crear una red de tipo bridge

```
docker network create <nombre red> -d bridge
```

### Crear un contenedor vinculado a una red

```
docker run -d --name <nombre contenedor> --network <nombre red> <nombre imagen>
```

### Para saber a qué red está conectado un contenedor

```
docker inspect <nombre contenedor>
```
ó
```
docker network inspect <nombre red> 
```

### Vincular contenedor a una red
```
docker network connect <nombre red> <nombre contenedor>
```

### Para desvincular un contenedor de una red
```
docker network disconnect <nombre red> <nombre contenedor>
```

### Para listar las redes existentes
```
docker network ls
```

### Crear los contenedores y las redes que se presentan en el esquema. Usar para todos los contenedores la imagen de nginx:alpine

![Imagen](esquema-ejercicio-redes.PNG)

# COLOCAR UNA CAPTURA DE LAS REDES EXISTENTES CREADAS

<img width="792" height="280" alt="image" src="https://github.com/user-attachments/assets/2217b7ac-430c-4270-aff0-22e3ea4cabdd" />


# COLOCAR UNA(S) CAPTURAS(S) DE LOS CONTENEDORES CREADOS EN DONDE SE EVIDENCIE A QUÉ RED ESTÁN VINCULADOS

## Creación de los contenedores en la red 

<img width="1043" height="137" alt="image" src="https://github.com/user-attachments/assets/96bcc813-a971-4310-ae29-ab5c4703f7e0" />

## Creación del contenedor en la red curso01

<img width="1058" height="47" alt="image" src="https://github.com/user-attachments/assets/61adf29c-466f-4ed7-ab5e-d37e5f763fb5" />

## Para ver en que red estan los contenedores 

Red curso01

<img width="1690" height="907" alt="image" src="https://github.com/user-attachments/assets/ad882875-c69e-4c95-bcc8-06106f589138" />

<img width="1842" height="1002" alt="image" src="https://github.com/user-attachments/assets/eab3e81d-973f-4b9c-8ca4-6aeaf63cc2ab" />

Red curso02

<img width="1862" height="1007" alt="image" src="https://github.com/user-attachments/assets/bb0a4c73-1cad-46c0-a2a1-bc70f1269fd8" />

### Para eliminar las redes creadas curso02
```
docker network rm <nombre de la red>
```

