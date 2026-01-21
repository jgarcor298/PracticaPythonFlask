# Documentación Práctica Python con Flash

**Autor:**  Jorge Garre Corrales


## Tarea

Para comenzar la práctica he creado un fichero Vagrantfile en el que he hecho dos bloques de provisión, uno para que ejecute comandos como root y otro para que los ejecute como vagrant

![](assets/20260116_125948_image.png)

Una vez arrancada la máquina he instaldo el gestor de paquetes pip

![](assets/20260116_130315_image.png)

Despues he instalado pipenv

![](assets/20260116_130421_image.png)

Y he comprobado que se ha instalado correctamente

![](assets/20260116_131018_image.png)

He instalado python-dotenv

![](assets/20260116_131239_image.png)

He creado el directorio del proyecto y le asignado los permisos

![](assets/20260116_132139_image.png)

He creado el fichero .env con su contenido

![](assets/20260116_132249_image.png)

Y lo he copiado en /vagrant/config para poder copiarlo al crear la máquina a través del provisional

He iniciado el entorno virtual

![](assets/20260116_132954_image.png)

Y he instalado las dependencias para el proyecto

![](assets/20260116_133216_image.png)

He creado los ficheros de la aplicación, los he copiado a mi ordenador para poder editarlos mas comodamente y luego los he vuelto a copiar dentro de la máquina

![](assets/20260116_135500_image.png)

Después he lanzado la aplicación

![](assets/20260116_140113_image.png)

Y he comprobado en el navegador que se ha lanzado correctamente

![](assets/20260116_140449_image.png)

Despues he probado también ha lanzarla con gunicorn

![](assets/20260116_141821_image.png)

Y he comprobado de la misma forma que funciona

![](assets/20260116_141843_image.png)

Sacamos la ruta desde donde se ejecuta gunicorn

![](assets/20260116_142419_image.png)


He lanzado y comprobado el que se ha lanzado nginx

![](assets/20260121_192940_image.png)


He creado el fichero flask_app.service en mi carpeta /vagrant/config/ y lo he copiado en la máquina Vagrant

![](assets/20260121_193502_image.png)



Despues he lanzado el servicio que he creado

![](assets/20260121_194834_image.png)


Con nano he creado el fichero app.conf con la siguiente configuración

![](assets/20260121_195116_image.png)


He creado el enlace simbólico del archivo de sitios webs

![](assets/20260121_195237_image.png)


He comprobado que la configuración de nginx esta correcta

![](assets/20260121_195342_image.png)


He modificado el fichero /etc/hosts de mi máquina anfitriona

![](assets/20260121_195607_image.png)


Y he comprobado que funciona 

![](assets/20260121_195636_image.png)



## Tarea de ampliación

Para la tarea de ampliación he partido de la máquina Vagrant como la tenía antes, y he empezado igual que antes

![](assets/20260121_200109_image.png)



He creado el fichero .env con esta configuración 

![](assets/20260121_200431_image.png)


He creado y activado el entorno virtual

![](assets/20260121_200537_image.png)


He instalado las dependencias del proyecto

![](assets/20260121_200703_image.png)


He probado la aplicación con Flask

![](assets/20260121_200746_image.png)



![](assets/20260121_200801_image.png)


He probado que funciona con gunicorn

![](assets/20260121_200857_image.png)



![](assets/20260121_200911_image.png)


He comprobado cual es la ruta del proyecto con gunicorn

![](assets/20260121_200956_image.png)



He creado el servicio systemd para hacer
