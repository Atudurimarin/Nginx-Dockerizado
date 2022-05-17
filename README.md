# Nginx-Dockerizado

1.Hacemos un docker pull nginx para descargar el Nginx en Docker <br><br>
![Ngnx1](https://user-images.githubusercontent.com/91564326/168905011-c787d49d-3198-44a1-8f73-edb1aaa61b94.png)<br><br><br>
2.Comenzamos la ejecución del contenedor como un demonio (-d) y publicamos el puerto 8080 en la red del host con el comando 
docker run --rm -d -p 8080:80 --name web nginx <br><br>
![Ngnx2](https://user-images.githubusercontent.com/91564326/168905787-e9149994-821a-4723-8c7a-ee5bfe091011.png)<br><br><br>
3. Visitamos http://localhost:8080 en el navegador para confirmar que tenemos el Nginx funcionando. <br><br>
![Ngnx3](https://user-images.githubusercontent.com/91564326/168906154-17e07cb0-ab92-4b5d-bb55-bc8c4e3c323c.png)<br><br><br>
4.Hacemos un docker stop web para parar la ejecución del contenedor que hemos llamado web. <br><br>
![Ngnx4](https://user-images.githubusercontent.com/91564326/168906526-0be04300-53fc-4199-8afa-f0a1391f55e9.png)<br><br><br>
5.Creamos un directorio en Documentos llamado nginx y dentro otro directorio llamado site-content. En este directorio, agregamos un archivo index.html e introducimos nuestro html.<br><br>
5.1 Montamos nuestro directorio local ~/Documentos/nginx/site-content localmente en el contenedor en ejecución en: /usr/share/nginx/html.<br><br><br>
5.2 Volvemos a cargar http://localhost:8080 en el navegador y observamos nuestro html.<br><br>
![Ngnx5](https://user-images.githubusercontent.com/91564326/168908068-3e6c3f43-cb72-4cad-abae-79f110505df6.png)<br><br><br>
6.Creamos un archivo llamado Dockerfile y pegamos los siguientes comandos: FROM nginx:latest
COPY ./site-content/index.html /usr/share/nginx/html/index.html<br><br>
6.1 Para construir nuestra imagen, ejecutamos el siguiente comando:

docker build -t webserver .<br><br><br>
![ngnx7](https://user-images.githubusercontent.com/91564326/168908819-6fb9c3be-c6c7-4db7-a025-14becd4a8835.png)<br><br><br>
7. Volvemos a visitar http://localhost:8080 y vemos como se ejecuta la imagen desde el Dockerfile.<br><br>
![Ngnx5](https://user-images.githubusercontent.com/91564326/168909836-5161467c-98dc-4798-9bec-2bb67450ae1e.png)


