# Practica Docker 2
 


[TOC]

### 1. Descarga las siguientes imágenes: ubuntu:18.04 , httpd , tomcat:9.0.39-jdk11 , jenkins/jenkins:lts , php:7.4-apache . 

```bash
daw@daw-docker:~$ docker pull ubuntu:18.04
daw@daw-docker:~$ docker pull php:7.4-apache
daw@daw-docker:~$ docker pull jenkins/jenkins:lts
daw@daw-docker:~$ docker pull tomcat:9.0.39-jdk11
daw@daw-docker:~$ docker pull httpd
```

### 2. Muestras las imágenes que tienes descargadas. 

![image-20230118095349858](assets/image-20230118095349858.png)

### 3. Crea un contenedor demonio con la imagen php:7.4-apache 



```bash
daw@daw-docker:~$ docker run -d --name Demonphp php:7.4-apache
```

### 4. Comprueba el tamaño del contenedor en el disco duro. 

![image-20230118095854341](assets/image-20230118095854341.png)

### 5. Con la instrucción docker cp podemos copiar ficheros a o desde un contenedor. 

#### a)Crea un fichero en tu ordenador, con el siguiente contenido: 

```php
<?php
echo phpinfo();
?>
```

```bash
daw@daw-docker:~$ cd Documentos
daw@daw-docker:~/Documentos$ nano archivo.txt
daw@daw-docker:~/Documentos$ ls
info.php
```

#### b)Copia un fichero info.php al directorio /var/www/html del contenedor con docker cp . 

```bash
daw@daw-docker:~/Documentos$ docker cp info.php Demonphp:/var/www/html
```

### 6. Vuelve a comprobar el espacio ocupado por el contenedor. 

![image-20230118101714580](assets/image-20230118101714580.png)

### 7.Accede al fichero info.php desde un navegador web

![image-20230118103527073](assets/image-20230118103527073.png)
