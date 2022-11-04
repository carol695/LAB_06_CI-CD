## Escuela Colombiana de Ingeniería

## Laboratorio CI/CD Azure DevOps

## INTEGRANTES 

* Carol Tatiana Cely 
* Julian Andres Largo 

____________________________________

En este laboratorio, se aprendió  cómo puede usar Azure Pipelines para implementar una aplicación web Java en Apache Tomcat con una base de datos MySQL en Azure. Apache Tomcat es un contenedor de servlets de Java de código abierto desarrollado por Apache Software Foundation (ASF). MySQL es un sistema de gestión de bases de datos relacionales de código abierto muy popular.

Para este laboratorio, se utilizó un Azure App Service y Azure Database for MySQL, un servicio de base de datos relacional basado en el motor del servidor MySQL de código abierto. Es una base de datos como servicio completamente administrada, capaz de manejar cargas de trabajo de misión crítica con un rendimiento predecible y escalabilidad dinámica.

### Ejercicio 1: creación de una aplicación web de Azure y una base de datos MySQL

Para desplegar un grupo de recursos ingresamos el siguiente comando 

![image](https://user-images.githubusercontent.com/63822072/200034929-6673fe5d-d9c6-43c2-8e9a-0034902bba05.png)

Creamos un App service plan, introducimos el comando y esperamos el registro 

![image](https://user-images.githubusercontent.com/63822072/200035050-ed08af0c-3a94-4752-b285-44352cf53628.png)

Creamos la web app, en este caso la nombramos como “AmazingAppCVDS” 

![image](https://user-images.githubusercontent.com/63822072/200035163-09336c87-92d1-45fe-aa42-9f7066c6a3de.png)

Ahora creamos un MYSQL server con un nombre, usuario y contraseña propias 

![image](https://user-images.githubusercontent.com/63822072/200035278-25a02885-139d-4b67-b293-eff54c7a4d96.png)

Ahora localizamos el grupo de recursos 

![image](https://user-images.githubusercontent.com/63822072/200035379-6ce76798-0807-4746-9ef5-ac91eb268813.png)

Seleccionamos el sql server 

![image](https://user-images.githubusercontent.com/63822072/200035461-fae1e833-fb68-4531-a60e-5439302312f9.png)

Vamos a propiedades y buscamos el nombre del servidor y lo tenemos presente 

![image](https://user-images.githubusercontent.com/63822072/200035537-fedfebf7-36c1-4b17-b63f-ba5639feaaed.png)

Luego vamos a seguridad de la conexión y habilitamos el acceso a los servicios Azure y luego guardamos 

![image](https://user-images.githubusercontent.com/63822072/200035794-ecebd7d4-b98d-4045-8e30-7d5b19af6991.png)

Vamos ahora a la app 

![image](https://user-images.githubusercontent.com/63822072/200035916-e31f481f-6e44-42b9-87c4-465c03875af8.png)

### Ejercicio 2: Actualización de la configuración de la aplicación para la aplicación web

Vamos a configuración y seleccionamos como Stack Java y demás versiones 

![image](https://user-images.githubusercontent.com/63822072/200036228-7f3fa1df-6bbf-4620-a998-4332958e5dcb.png)

Veremos la web page 

![image](https://user-images.githubusercontent.com/63822072/200036285-04351ccc-873e-4fe8-a96a-f8b2655ed66d.png)

Ahora vamos a conectar con la base de datos, por lo cual lo haremos desde el portal de azure y crearemos una nueva connection string 

![image](https://user-images.githubusercontent.com/63822072/200036398-30368dea-d004-4cd3-8e23-74f4db30ab41.png)

Ponemos el nombre y el valor para la conexión y guardamos 

![image](https://user-images.githubusercontent.com/63822072/200036461-0b1f1825-1bb5-4297-ab91-25147cffd65c.png)

### Ejercicio 3: implementar los cambios en la aplicación web

Ahora vamos al proyecto creado y elegimos Pipeline y luego MyShuttleBuild y luego editar 

![image](https://user-images.githubusercontent.com/63822072/200036542-a07d6d3a-5284-4f66-82fb-201da57d76e1.png)

Luego seleccionamos Maven y luego queue para empezar 

![image](https://user-images.githubusercontent.com/63822072/200036844-614d7df7-3dae-4f07-8ac9-b8b6dee0bb5b.png)

![image](https://user-images.githubusercontent.com/63822072/200036921-e58ba194-6916-4b40-9eae-cda8c90db1d9.png)

Esperemos un momento que se ejecute el pipeline y corra con normalidad 

![image](https://user-images.githubusercontent.com/63822072/200037081-6ec99af8-e1b9-4c78-b695-0a8df8e997df.png)

Luego vamos a releases y seleccionamos MyShuttleRelease y la editaremos 

![image](https://user-images.githubusercontent.com/63822072/200037135-d1a467eb-bb7b-4620-b7d3-cbea9e8f9e7d.png)

Borramos los reléase existentes y hacemos uno nuevo 

![image](https://user-images.githubusercontent.com/63822072/200037206-068f9e7e-4528-4c07-a2d8-ada40a3f64ec.png)

Configuramos la base de datos y el deploy de la web app 

![image](https://user-images.githubusercontent.com/63822072/200037264-117dc9fc-8d05-4711-8a48-baecc7ac77d8.png)

![image](https://user-images.githubusercontent.com/63822072/200037294-218dde95-c52d-492d-9556-e6c083a98717.png)

Luego de configurar el artefacto haremos el deploy, donde esperaremos un tiempo 

![image](https://user-images.githubusercontent.com/63822072/200037341-44a3a35a-f1f3-45a8-a8e0-f4f09f6bc0f0.png)

Ahora una vez que todo funciona correctamente nos conectaremos al sitio y haremos login 

![image](https://user-images.githubusercontent.com/63822072/200037686-183c361a-c398-4515-8f2a-579584c5b1a1.png)

Donde para nuestro caso hay un error en el login que seguramente se esta dando por la conexión a la base de datos 

![image](https://user-images.githubusercontent.com/63822072/200037737-185f7446-4295-47b2-a22e-f95c96fe7cc5.png)

### URL DEL SITIO DESPLEGADO 

http://amazingappcvds.azurewebsites.net/myshuttledev/



