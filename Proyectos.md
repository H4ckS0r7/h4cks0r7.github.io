[Home](index.md) | [Proyectos](Proyectos) | [Sobre nosotros](sobrenosotros) | [H4ck2P](h4ck2p) | [S3RGI09](https://s3rgi09.github.io/)

# Proyectos
## Hidden Web Server
Estoy seguro de que alguna vez has echo un ```sudo service apache2/nginx start``` para crear un servidor web, pero, lo has echo en la red Tor? Pues aqui te enseñamos como.
Paso 1: Edita tu archivo *torrc* y añade estas dos lineas 
```HiddenServiceDir /var/lib/tor/my_website/
HiddenServicePort 80 127.0.0.1:80
HiddenServiceDir /var/lib/tor/my-website/
HiddenServicePort 80 unix:/var/run/tor-my-website.sock```
Paso 2: Ahora guarda tu ```torrc``` y reinicialo con el siguiente comando ```sudo systemctl restart tor``` Si Tor inicia nuevamente, bien. De lo contrario, hubo un error. Primero mira en tus archivos de registro por pistas. Va a mostrar algunas alertas o mensajes de error. Eso debería darte alguna idea de cuál fue el error. Típicamente, hay errores de sintaxis en
```torrc``` o permisos de directorios incorrectos
Paso 3: Ahora, para obtener su dirección de ```Onion Service```, vaya a su ```HiddenServiceDirdirectorio``` y busque un archivo llamado ```hostname```. El "hostnamearchivo" en su directorio de configuración de ```Onion Service``` contiene el nombre de host para su nuevo servicio de cebolla v3. Los otros archivos son sus claves de ```Onion Service```, por lo que es imperativo que se mantengan privados. Si sus claves se filtran, otras personas pueden hacerse pasar por su Servicio Onion, considerándolo comprometido, inútil y peligroso para visitar.
