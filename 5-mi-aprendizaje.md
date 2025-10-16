# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Antes de realizar la práctica, tenía un conocimiento general sobre el funcionamiento de los contenedores en Docker por la practica N°1, pero no tenía un conocimientp sobre los aspectos específicos en este caso los tipos de red y el uso de variables de entorno.
Después de realizar la práctica, comprendí mejor cómo Docker maneja la comunicación entre contenedores mediante la red bridge (es la red por defecto en Docker y permite que los contenedores se comuniquen entre sí dentro del mismo host) y como se puede personalizar la red y cómo configurar variables de entorno para hacer las aplicaciones más seguras.


Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).

Docker Secrets es una funcionalidad que permite almacenar, distribuir y gestionar datos sensibles de forma segura dentro de entornos Docker, especialmente en Docker Swarm (modo de orquestación de servicios).Estos secretos se almacenan encriptados en el gestor de Docker y solo se montan en servicios autorizados como archivos temporales en memoria (por defecto en /run/secrets/).
Los secretos no se guardan dentro de la imagen, ni se transmiten en texto plano, lo que reduce el riesgo de exposición accidental.

**Comandos Básicos**
echo "clave123" | docker secret create mi_clave -   //crear un secreto 
docker secret ls   //ver los resultados disponibles 
docker secret inspect mi_clave    //Inspeccionar un secreto
/run/secrets/mi_clave    //Acceder al secreto dentro del contenedo
docker secret rm mi_clave    //Elominar un secreto 

Por lo tanto, Docker Secrets ofrece un mecanismo seguro y profesional para gestionar credenciales dentro de entornos Docker, mejorando la seguridad, portabilidad y confiabilidad de las aplicaciones en producción.
Es una práctica recomendada frente al uso de variables de entorno cuando se manejan datos sensibles.



