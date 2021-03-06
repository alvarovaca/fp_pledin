---
title: "Realización y restauración de copias de seguridad en linux"
permalink: /seguridadgm/u04/linux.html
---

Vamos a crear diferentes tipos de copias de seguridad con el comando de linux `tar`. Los siguientes enlaces te pueden ayudar a aprender como hacer copias totales, diferenciales e incrementales con tar:

* [Backups con tar: fullbackups, incrementales y diferenciales](https://nebul4ck.wordpress.com/2015/03/20/backups-con-tar-full-backups-e-incrementales/)
* [Backup y restauración de backups incrementales con tar](http://systemadmin.es/2015/04/backup-y-restauracion-de-backups-incrementales-con-tar)

## Copias incrementales

1. Crea una carpeta llamada `datos` con tres ficheros con distintos contenidos:

        fichero1.txt
        fichero2.txt
        fichero3.txt

2. Primer día: Realiza una copia completa de esa carpeta con el comando tar (los ficheros lo vamos a ir numerando como si las copias la hiciéramos en distintos días, es decir el fichero resultante se llamaría `copiacompleta1.tgz`).

3. Segundo día: Modifica el `fichero1.txt`, borra el `fichero2.txt` y crea un nuevo fichero `fichero4.txt`. Realiza una copia incremental del directorio (`copiaincremental2.tgz`).
4. Tercer día: Modifica el `fichero3.txt` y crea un nuevo fichero `fichero5.txt`. realiza un copia incremental del directorio (`copiaincremental3.tgz`). 
5. Cuarto día: Crea un directorio `carpeta1` y dentro crea un nuevo fichero `fichero6.txt`. Realiza una copia incremental del directorio (`copiaincremental4.tgz`).
6. Quinto día: Borra el `fichero1.txt` y renombre la carpeta a `carpeta2`. Realiza una copia incremental del directorio (`copiaincremental5.tgz`).
7. Sexto día: Realiza otra copia completa del directorio (`copiacompleta6.tgz`).
8. Séptimo día: Crea otro directorio `carpeta3` y dentro el fichero `fichero6.txt`. Borra el `fichero4.txt`. Realiza una copia incremental del directorio (`copiaincremental7.tgz`).
9. Octavo día: Borra el `fichero5.txt`. Realiza una copia incremental del directorio (`copiaincremental8.tgz`).

Una vez tenemos nuestras copias, imaginemos que hemos tenido un problema de seguridad y hemos perdido la carpeta `datos`. Recupera la información de la carpeta `datos` para que aparezcan los ficheros que había:

* El octavo día.
* El quinto día.
* El tercer día.

## Copias diferenciales

Realiza el mismo ejercicio ejercicio, pero ahora realizando copias diferenciales.
Responde a las siguiente pregunta: ¿Ocupan más las copias diferenciales o las copias incrementales?

## Copias mixtas

Vamos a repetir el ejercicio, realizando las mismas modificaciones a los ficheros, pero realizando las siguientes copias:

* Primer día: Copia completa
* Segundo día: Copia incremental
* Tercer día: Copia incremental
* Cuarto día: Copia diferencial
* Quinto día: Copia incremental
* Sexto día: Copia incremental
* Séptimo día: Copia diferencial
* Octavo día: Copia incremental

Realiza las mismas restauraciones.

## Automatización de copias de seguridad utilizando cron

1. Busca información para crear 3 scripts en bash para crear una copia completa, incremental y diferencial de la carpeta `datos`. Los nombres de los ficheros generados deben contener la fecha. 
2. Explica el funcionamiento de `cron` y documenta cómo lo utilizaríamos para automatizar el proceso de copia de seguridad según el siguiente esquema:

* Todos los lunes a las 0:00 de la noche se realiza una copia completa.
* Todos los días (menos los lunes y jueves) se realiza una copia incremental a las 21:00 horas.
* Todos los jueves se realiza un copia diferencial a las 21:00 horas.

## Copias de seguridad en linux con programas de terceros

Busca alguna herramienta que facilite la realización de copias de seguridad bajo Linux. Puede ser una herramienta gráfica o bien un sistema integrado para copias de seguridad. Comenta sus características y las ventajas e inconvenientes que tendría sobre los comandos anteriores. realiza el ejercicio anterior con este nuevo programa.

