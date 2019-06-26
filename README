# sintel
Inteligencia sobre series y otros medios

## Introducción

Sintel es un script complejo que está pensado para servir de apoyo a otros scripts que serán mucho más sencillos precisamente porque sintel hace el trabajo sucio.

Básicamente sintel maneja una base de datos de medios. Cuando hablo de medios me refiero a archivos de vídeo mayormente y en concreto películas y series. Este script permite llevar la gestión de todas las películas y series que tenemos descargadas en nuestro ordenador. 

Además este script está diseñado para ser modular y extensible de forma sencilla.

## Instalación

La instalación se efectúa clonando el repositorio y modificando algunas variables dentro de algunos archivos del script.

### Clonamos el repositorio

Si vamos a tener nuestros scripts en la carpeta bin que reside en la carpeta personal. Es decir, en vuestra home, lo que yo recomiendo para no ensuciar esta carpeta es crear una carpeta dentro de ella que se llame 'scripts', por ejemplo. Nos metemoe en ella y clonamos con el siguiente comando:

---

git clone https://github.com/mhyst/sintel.git

---

El clonado creará una carpeta llamada 'sintel' que deberemos conservar pues dentro están los diversos archivos que conforman este complejo script.

### Ajustamos las variables del script

Entramos en 'sintel' y deberemos modificar el contenido de las siguientes variables:

- global-DIR: Ubicada en el archivo sintel. Si tienes el script en ~/bin/scripts/sintel tal como explico en el párrafo de arriba, no es necesario modificarla. Si no es así, debemos indicar la ruta completa en la que residen los archivos de sintel.

- database_DB: Ubicada en el archivo database. Contendrá la ruta completa del archivo de la base de datos. Este archivo debe estar dentro de la carpeta indicada en global-DIR. Debe incluir el nombre del fichero.

- torrents_SERVER: Ubicada en torrents. Contiene la ip y el puerto del control remoto de transmission. Solo es necesario modificar esta variable si vamos a usar el módulo que permite comunicarse con el gestor de torrents transmission.

- PLAYER: Ubicada en ver. Permite configurar con qué reproductor queremos reproducir las películas y series.

### Copiamos el archivo sintel a la carpeta bin

Una vez que todas las variables han sido modificadas solo nos resta copiar únicamente el archivo sintel a la carpeta bin que habíamos seleccionado previamente para poder invocar sintel desde cualquier carpeta. Si nuestra carpeta bin va a estar dentro de nuestra carpeta personal, siendo el usuario en mi caso 'mhyst', el comando quedaría como sigue:

---

cp sintel  ~/bin/

---

Para que el comando funcione debemos estar dentro de la carpeta sintel. Y ya está. ¡Instalación completada!

## Usos de sintel

