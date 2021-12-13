Run Php application on Docker

Create docker file
FROM php:7.2-apache
COPY index.php /var/www/html/index.php
EXPOSE 80
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]

Code Explain
	1	The base image php:7.2-apache is used. The base image is pulled from dockerhub.
	2	The file index.php is copied to /var/www/html/ in the image.
	3	The port 80 is exposed for apache.
	4	Apache is started inside the container.

Create index.php file
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body style="background-color: gray">
<h1 style="color:white;text-align: center;">
<?php echo "Hi, I am running on Docker....😆"?>
</h1>
</body>
</html>

Build docker image
docker build -t devops-with-me:v1 .

Run image
docker run -d -p9090:80 devops-with-me:v1

localhost:9090
