<!--
[//]: # This file is part of Sintel.
[//]: #
[//]: # Sintel is free software: you can redistribute it and/or modify
[//]: # it under the terms of the GNU General Public License as published by
[//]: # the Free Software Foundation, either version 3 of the License, or
[//]: # (at your option) any later version.
[//]: #
[//]: # Sintel is distributed in the hope that it will be useful,
[//]: # but WITHOUT ANY WARRANTY; without even the implied warranty of
[//]: # MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
[//]: # GNU General Public License for more details.
[//]: #
[//]: # You should have received a copy of the GNU General Public License
[//]: # along with Sintel.  If not, see <https://www.gnu.org/licenses/>.
[//]: #
[//]: #-->
# sintel
Inteligencia sobre series y otros medios

## Introducción

Sintel es un script complejo que está pensado para servir de apoyo a otros scripts que serán mucho más sencillos precisamente porque sintel hace el trabajo sucio.

Básicamente sintel maneja una base de datos de medios. Cuando hablo de medios me refiero a archivos de vídeo mayormente y en concreto películas y series. Este script permite llevar la gestión de todas las películas y series que tenemos descargadas en nuestro ordenador. Además hay dos módulos: anime y veronline que permiten hacer seguimiento del anime o series que vemos online sin descargarnos los archivos. Estos dos módulos cuentan con sendos frontend que se pueden encontrar en [este repositorio](https://github.com/mhyst/anime).

Además este script está diseñado para ser modular y extensible de forma sencilla.

## Instalación

**¡ATENCIÓN!**: Si ya tenía una copia de sintel instalada, antes de efectuar la actualización haga una copia de seguridad de la base de datos que se encuentra en /usr/share/sintel/sintel.db. Entonces actualice y restaure su copia de la base de datos. Después ejecute el comando 'sintel -f init' para actualizar la base de datos a la nueva versión. Si va a actualizar a la versión 2.6.0-5 o posterior, esta medida no es necesaria.

### Método 1

Desgargamos el paquete deb de la última release y ejecutamos un comando similar a este:

```
sudo dpkg -i sintel_2.6.0-5_all.deb
```

### Método 2

Agregando mi propio repositorio. Este es el mejor método ya que una
vez instalado podremos disponer de actualizaciones como si se tratara
de cualquier otro paquete.

```
sudo add-apt-repository ppa:mhysterio/bash
sudo apt-get update
apt install sintel
```

Los paquetes del ppa está firmados con mi clave personal secreta cuyo
fingerprint es el siguiente: 

```
Huella de clave = 018A BA44 9EC5 3A05 74D4  2A03 D18F A7B9 26CD 0212
uid                  Julio Cesar Serrano Ortuno (mhyst) <mhysterio@gmail.com>
```

### Método 3

Este método consiste en una instalación manual. La instalación se efectúa
mediante el clonado del repositorio. También deberemos editar un par de
archivos y modificar algunas variables del script.

#### Clonamos el repositorio

```
cd /tmp
git clone https://github.com/mhyst/sintel.git
```

El clonado creará una carpeta llamada 'sintel' que deberemos conservar pues dentro están los diversos archivos que conforman este complejo script.

#### Ajustamos las variables del script

Entramos en 'sintel' y deberemos modificar el contenido de las siguientes variables con nuestro editor preferido (por ejemplo nano o vim):

- global-DIR: Ubicada en el archivo sintel. Si tienes el script en ~/bin/scripts/sintel tal como explico en el párrafo de arriba, no es necesario modificarla. Si no es así, debemos indicar la ruta completa en la que residen los archivos de sintel.

- torrents_SERVER: Ubicada en torrents. Contiene la ip y el puerto del control remoto de transmission. Solo es necesario modificar esta variable si vamos a usar el módulo que permite comunicarse con el gestor de torrents transmission.

- PLAYER: Ubicada en ver. Permite configurar con qué reproductor queremos reproducir las películas y series.

Ahora volveremos a la carpeta /tmp/ con:

```
cd ..
```

#### Movemos la carpeta a su lugar definitivo

El directorio sintel que acabamos de crear en /tmp/ deberá moverse
a su localización definitiva. Nosotros lo haremos en $HOME/.local.


```
mv sintel $HOME/.local/

```

#### Copiamos el archivo sintel a la carpeta bin

Por último debemos poner el archivo llamado 'sintel' en una de las
carpetas que se encuentran mencionadas en la variable PATH. Por
practicidad vamos a elegir $HOME/bin. Si no existe la creamos

```
cd
mkdir bin
cp ./local/sintel/sintel  $HOME/bin/
```

## Usos de sintel

- Popular la base de datos: Esto se puede hacer tantas veces como se quiera con distintas localizaciones del sistema de archivos o con las mismas. Sintel es capaz de detectar medios y episodios que ya están en la base de datos para evitar almacenarlos repetidamente.

```

sintel -d /home/mhyst/Peliculas
sintel -d /mnt/series

```

- Listar medios

```

sintel --list-all            # Lista todos los medios
sintel --list-series         # Lista series
sintel --list-peliculas      # Lista las películas
sintel --list-episodios 120  # Lista los episodios de la serie con el id 1

```

- Buscar medios

```
sintel --find-series poirot
sintel --find-peliculas "400 golpes"

```

- Listar funciones: permite echar un ojo a las funciones disponibles para invocar

---

sintel -l

---

- Invocar una función

Es posible invocar cualquiera de las funciones que aparecen en el resultado del comando anterior. El problema es que apenas si hay documentación, lo que hace complicado su uso para otra persona que no sea yo mismo. Habrá que tener un poco de paciencia hasta que diseñe una documentación apropiada. Estoy en ello.

---

sintel -n ver.serie:goliath

---


