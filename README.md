# tienda-perritos
EV2 DevOps

La empresa Innovatech Chile ha decidido continuar a la etapa 2 del proyecto, es por eso que su equipo de trabajo deberá poder
desplegar la aplicación de una de las marcas de la empresa en la infraestructura construida en la Evaluacion Parcial N 1, para
esto la empresa ha solicitado los siguientes requerimientos técnicos:

1. Contenedorización de Frontend y Backend
▪ Cada uno de los repositorios entregados (Frontend y Backend) debe incluir toda la estructura necesaria para ejecutar los
proyectos dentro de contenedores, lo que implica:
▪ Un Dockerfile correctamente construido (idealmente con multi-stage build).
▪ Un archivo docker-compose.yml que permita levantar los servicios asociados.
▪ Configuración de variables de entorno, puertos, dependencias y volúmenes según corresponda.
▪ Los proyectos deben ser capaces de ejecutarse de forma independiente y conjunta en entornos contenerizados.

2. Persistencia de datos
▪ Se debe aplicar persistencia de datos utilizando volúmenes Docker definidos en los archivos docker-compose.
▪ Los volúmenes deben permitir que la información crítica del Backend o la base de datos no se pierda al reiniciar contenedores.
▪ Debe justificarse la elección de los volúmenes (bind mount vs. named volume).

3. Pipeline de Integración y Despliegue Continuo (CI/CD)
▪ Cada repositorio (frontend y backend) debe contener toda la configuración necesaria para ejecutar correctamente los
pipelines de integración continua y despliegue continuo, lo cual debe incluir:
▪ Archivo de workflow en GitHub Actions que:
o Construya la imagen Docker.
o Publique la imagen en ECR o Docker Hub.
o Despliegue automáticamente la actualización en la instancia EC2 correspondiente.
▪ Manejo adecuado de secrets (credenciales, tokens, variables).
▪ Uso de triggers basados en la rama deploy.
▪ Pasos claros y documentados en el pipeline.

4. Funcionamiento del contenedor en las instancias EC2
▪ Instancia Frontend
▪ Debe ejecutarse correctamente el contenedor asociado a la imagen publicada por el docente
▪ El contenedor debe iniciar sin errores y ser accesible desde el navegador mediante el dominio o la IP pública de la instancia.
▪ Debe comprobarse la correcta lectura de variables, puertos expuestos y reglas de acceso.
▪ Instancia Backend
▪ Debe ejecutarse correctamente el contenedor asociado a la imagen publicada por el docente
▪ El Backend debe:
o Conectarse correctamente al contenedor de base de datos.
o Responder a las peticiones provenientes del Frontend.
o Mantener su persistencia según los volúmenes configurados.

5. Visualización e integración del Frontend con el Backend
▪ Debe demostrarse funcionalmente que:
▪ El Frontend puede visualizarse sin errores desde el navegador.
▪ El Frontend se comunica correctamente con el Backend desplegado en la subred privada.
▪ Los endpoints utilizados por el Frontend funcionan mediante el dominio/IP configurado en la instancia Front.
▪ La comunicación Front → Back debe respetar las políticas de seguridad definidas en los Security Groups.
