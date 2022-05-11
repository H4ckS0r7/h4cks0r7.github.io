# Proyectos
[Home](index.md) | [Proyectos](proyectos)
# Manual de instrucciones de Scan
![Añadir un subtítulo](https://user-images.githubusercontent.com/96842235/167315668-5b6290ae-3acd-451e-abb4-10b2fd353a23.png)

Herramienta para escanear puertos de una IP. El script escrito en python funciona gracias a la libreria "Python-nmap" que puede ver en la web Indices de Paquetes de Python (PyPI) e instalar con pip, lo comodo de esto es que no es necesario hacer todo esto, ya que el repositorio tiene un pequeño script llamado "instalacion.sh" para automatizar todas estas tareas y darle permisos de ejecucion al script.

---------------------------------------------------------------------------------------------------------------------------------------------------------

# Como hacer un escaneo
Hacer un escaneo con Nmap puede llegar a ser algo dificil para la gente que recien a empezado en la informatica por culpa de todos sus parametros, yo lo que recomiendo es que si estas aprendiendo NO UTILICES ESTE SCRIPT, ya que lo unico que aprenderias sera a tenerlo todo echo. Pero si eres un profesional o un aficionado con conceptos avanzados sobre Nmap y su sondeo, este script solo te hara ahorrar tiempo. Para iniciar un escaneo es muy simple, solo vete al directorio donde tienes el archivo del script y haz en tu consola "./scan.py" si le has asignado permisos de ejecucion, si no tendras que hacer un "python scan.py", de las dos maneras tendras el script corriendo, ahora solo pon la IP a la que quieres hacer el escaneo, en unos 2-3 segundos tendras los resultados del escaneo en tu pantalla.
![Captura de pantalla_2022-05-08_22-04-01](https://user-images.githubusercontent.com/96842235/167313797-12f5d574-fc3d-4f9b-85e2-3de28296440d.png)

---------------------------------------------------------------------------------------------------------------------------------------------------------

# No funciona el escaneo
Si el escaneo no funciona, asegurate de que tienes el paquete Python-nmap instalado, si no lo tienes haz un "pip install python-nmap".
Si aun asi no funciona y te sale un error de sintaxis o de nombre, copia el codigo de Scan desde GitHub a tu script de Scan, esto puede ser porque alguien o tu ha tocado el codigo de Scan y a puesto algo que bloquee otra cosa.
Si sigue sin funcionar y su pc o laptop tiene un hardware muy antiguo instale ScanLite, tambien en mi GitHub.

---------------------------------------------------------------------------------------------------------------------------------------------------------

# Como instalar Scan
Para instalar el script es muy simple y hay dos opciones. La primera y la más facil es ejecutar en tu terminal "bash instalacion.sh", este archvio es un pequeño script que sirve para realizar todas las tareas para utilizar correctamente Scan sin errores. Y la segunda es seguir un pequeño resumen de la instalacion que haremos aqui:

[Paso 1:] Vamos a empezar por lo basico, instalaremos la libreria Python-nmap, ponga en su consola: pip install python-nmap

[Paso 2:] Ahora hay que dar permisos de ejecucion al script y a todo lo necesario, ponga en su terminal los siguientes comandos, solo funciona en sistemas tipo UNIX-LIKE: chmod +x ./scan.py ./scan1.0.py RecoverScanScript.sh

[Paso 3:] Ya hemos acabado, ahora puede borrar el archivo instalacion.sh si quiere, ahora a hackear y a pasarlo bien.

---------------------------------------------------------------------------------------------------------------------------------------------------------

# Scan:Version 1.0
En este repositorio viene incluido la primera version del script Scan, esta version esta hay para que vea el avance, las mejoras y el contrastre desde la primera version a la ultima. No tiene nada util en el fondo ya que es mas lento que la ultima version y mas simple.
![Screenshot_2022-05-08_22_06_50](https://user-images.githubusercontent.com/96842235/167313912-a427bd67-7291-485b-89b2-b244dcc247f3.png)

---------------------------------------------------------------------------------------------------------------------------------------------------------

# RecoverScanScript
Este script creado en Bash sirve para recuperar el script Scan. Es una herramienta de recuperacion para solucionar errores por si a pasado algo en el paquete Python-nmap, como que no se a descargado correctamente. Este script borra todos los datos de la carpeta Scan y todos sus archivos dentro de la carpeta al igual que el paquete python nmap y reinstala el repositorio de github. Una vez instalado el repositorio, ejecuta el instalador de Scan, y se instala el paquete Python-nmap, se le da permisos de ejecucion a todos los archivos y se borra a si mismo para tener todo como el primer dia. esta herramienta esta pensada para resolver errores graves como un problema al instalar el repositorio o el paquete Python-nmap.

---------------------------------------------------------------------------------------------------------------------------------------------------------

# Fin
Le doy gracias a todo el mundo que a instalado Scan, a mi me alegra saber que estoy contribuyendo en ayudar a otras personas que comparten la misma pasion por la informatica que yo, la verdad, si yo hubiese tenido este script cuando habia aprendido medianamente nmap, me las habria gozado, literalmente podria estar ahora mismo en la carcel por haber hackeado la red wifi de el centro comercial de mi ciudad (Nunca lo e echo, NUNCA) espero que os halla servido esta informacion y sobre todo el script.

## Codigo:
```
#!/usr/bin/python3
import nmap
print("\033[2J\033[1;1f") # Borrar pantalla y situar cursor

print()
print("\033[1;31m"+"-----------------------------------")
print("\033[1;31m"+"| ___________________________   __|")
print("\033[1;31m"+"| __  ___/_  ____/__    |__  | / /|")
print("\033[1;31m"+"| _____ \_  /    __  /| |_   |/ / | github.com/S3RGI09")
print("\033[1;31m"+"| ____/ // /___  _  ___ |  /|  /  |")
print("\033[1;31m"+"| /____/ \____/  /_/  |_/_/ |_/   | V3.0")
print("\033[1;31m"+"|////////////////\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\|")
print("\033[1;31m"+"-----------------------------------")
print("\033[1;34m"+"        / \ / \ / \ / \ ")
print("\033[1;34m"+"       ( N | M | A | P )")
print("\033[1;34m"+"        \_/ \_/ \_/ \_/")
print("---------------------------------------------------------------------"+'\033[0;m')
print("\033[1;33m"+"[Info] Herramienta para escanear los puertos abiertos de una IP"+'\033[0;m')
print("\033[1;34m"+"  ||   Programada por S3RGI09 (Sergio Casero Verdial) "+'\033[0;m')
print("\033[1;35m"+"* Para equipos mas antiguos: ScanLite en mi github"+'\033[0;m')
print("\033[1;35m"+"* IG: s3rgi09__ | GitHub: S3RGI09")
print("\033[0;37;41m"+"[=] Script con licencia GNU GPL y Apache Licence"+'\033[0;m')
print("\033[5;1;31;40m"+"[!] Puede cancelar el escaneo en cualquier momento haciendo: [Ctrl+C]"+'\033[0;m')
print("\033[1;34m"+"---------------------------------------------------------------------"+'\033[0;m')
host= input("\033[1;32m"+"[+] IP Objetivo ==> "+'\033[0;m') 
print("\033[1;34m"+"---------------------------------------------------------------------")
nm= nmap.PortScanner()
puertos_abiertos="nmap -p "
results = nm.scan(hosts=host,arguments="-sT -n -Pn -T4")
count=0
#print (results)
print("\nHost : %s" % host)
print("Estado : %s" % nm[host].state())
for proto in nm[host].all_protocols():
	print("Protocolo : %s" % proto)
	print()
	lport = nm[host][proto].keys()
	sorted(lport)
	for port in lport:
		print ("Puerto : %s\tServicio : %s" % (port, nm[host][proto][port]["name"]))
		if count==0:
			puertos_abiertos=puertos_abiertos+str(port)
			count=1
		else:
			puertos_abiertos=puertos_abiertos+","+str(port)

print("\nPuertos abiertos: "+ puertos_abiertos +" "+str(host))
```

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
