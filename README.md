<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

# 1. Operaciones Basicas

### a. `export`
Despliega todas las variables de ambiente. Si necesitas los detalles de una variable especifica, utiliza `echo $NOMBRE_DE_VARIABLE`.

```bash
export
```
Ejemplo:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
whatis despliega  la descripcion para los comandos de usuario, llamadas del sistema, funciones de librerias y otros manuales de comandos.

```bash
whatis something
```
Ejemplo:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`
whereis realiza una busqueda de ejecutables, archivos de codigo fuente, manuales de pagina, utilizando una base de datos construida por el sistema de manera automatica.

```bash
whereis name
```
Ejemplo:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
which realiza una busqueda de ejecutables en los directorios especificados por la variable de ambiente PATH. Este comando despliega las rutas completas a los ejecutables.

```bash
which nombre_del_programa 
```
Ejemplo:
```bash
$ which php
/c/xampp/php/php
```

### e. clear
Limpia el contenido de la ventana.

## 1.1. Operaciones con Archivos
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-lpq">lpq</a></td>
      <td><a href="#m-lpr">lpr</a></td>
      <td><a href="#n-lprm">lprm</a></td>
      <td><a href="#o-ls">ls</a></td>
      <td><a href="#p-more">more</a></td>
      <td><a href="#q-mv">mv</a></td>
      <td><a href="#r-rm">rm</a></td>
      <td><a href="#s-tail">tail</a></td>
      <td><a href="#t-touch">touch</a></td>
   </tr>
</table>

### a. `cat`
Puede ser utilizado para los siguientes propositos bajo UNIX o Linux
  
* Mostrar archivos de texto en pantalla
* Copiar archivos de texto 
* Combinar archivos de texto 
* Crear nuevos archivos de texto 
```bash
cat nombredearchivo
cat archivo1 archivo2 
cat archivo1 archivo2 > nuevoarchivocombinado
cat < archivo1 > archivo2 #copiar archivo1 a archivo2
```

### b. `chmod`
El comando chmod significa "cambiar modo" y permite cambiar los permisos de lectura, escritura y ejecucion en los archivos y carpetas para mas información de este comando revisa este [enlace](https://ss64.com/bash/chmod.html).

```bash
chmod -options nombredearchivo
```

### c. `chown`
El comando chown significa "cambiar propietario" y permite cambiar el propietario de archivos y carpetas, los cuales pueden ser usuarios o grupos. El uso basico es muy simple, primero se especifica el usuario (propietario) y despues el grupo, separados por dos puntos. 

```bash
chown -options user:group nombredearchivo
```

### d. `cp`
Copia un archivo de un lugar a otro.
```bash
cp nombredearchivo1 nombredearchivo2
```
Donde `nombredearchivo1` es la ruta fuente a el archivo y   `nombredearchivo2` es la ruta destino del archivo.

### e. `diff`
Compara archivos y lista las diferencias.
 
```bash
diff nombredearchivo1 nombredearchivo2
```

### f. `file`
Determina el tipo de archivo.  
```bash
file filename
```
Ejemplo:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
Encuentra archivos en un directorio
```bash
find directory options pattern
```
Ejemplo:
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `gunzip`
Descomprime archivos comprimidos por gzip.
```bash
gunzip filename
```

### i. `gzcat`
Permite ver el contenido de un archivo gzipped sin tener que descomprimirlo.

```bash
gzcat filename
```

### j. `gzip`
Compresses files.  
```bash
gzip filename
```

### k. `head`
Outputs the first 10 lines of file  
```bash
head filename
```

### l. `lpq`
Revisar la cola de impresion.
```bash
lpq
```
Ejemplo:
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### m. `lpr`
Imprimir un archivo.
```bash
lpr filename
```

### n. `lprm`
Eliminar algo de la cola de impresion.  
```bash
lprm jobnumber
```

### o. `ls`
Lista archivos. `ls` tiene muchas opciones: `-l` lista archivos en 'formato largo', el cual contiene el tamaño exacto del archivo, quien es dueño del archivo, quien tiene permisos para verlo y cuando se modifico por ultima vez. `-a` lista todos los archivos, incluyendo los archivos ocultos. Para mas informacion de este comando revisa este [link](https://ss64.com/bash/ls.html).  

 
```bash
ls option
```
Ejemplo:
<pre>
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
</pre>

### p. `more`

Despliega la primera parte de un archivo (desplazarse con espacio y presiona q para salir).

```bash
more filename
```

### q. `mv`
Mueve un archivo de una localizacion a otra
```bash
mv filename1 filename2
```
Donde `filename1`  es la ruta origen de el archivo y `filename2` es la ruta destino del archivo.

Tambien puede ser utilizado para renombrar un archivo.

```bash
mv old_name new_name
```

### r. `rm`

Elimina un archivo. Si se utiliza este comando en un directorio se producira un error.
`rm: directory: is a directory`
Para eliminar un directorrio, se tiene que incluir la bandera `-r` el cual removera el contenido del directorio de manera recursiva. Se tiene la opcion de incluir la bandera `-f` para forzar el borrado por ejemplo, sin tener que dar una confirmacion.

```bash
rm filename
```

### s. `tail`
Da como salida las ultimas 10 lineas de un archivo. Se puede utilizar la bandera `-f` para agregar datos a la salida a medida que el archivo crece.
  
```bash
tail filename
```

### t. `touch`
Actualiza las marcas de tiempo de acceso y modificacion en el archivo. Si el archivo no existe se crea.


```bash
touch filename
```
Ejemplo:
```bash
$ touch trick.md
```

## 1.2. Text Operations

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-egrep">egrep</a></td>
      <td><a href="#e-fgrep">fgrep</a></td>
      <td><a href="#f-fmt">fmt</a></td>
      <td><a href="#g-grep">grep</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`
awk es el comando mas util para manejar archivos de texto. Opera en un archivo completo linea por linea. Por defecto utiliza el espacio en blanco para separar los campos. La sintaxis mas comun para el comando awk es 


```bash
awk '/search_pattern/ { action_to_take_if_pattern_matches; }' file_to_parse
```
Tomemos el siguiente archivo `/etc/passwd`. A continuacion se muestran los datos de ejemplo que contiene este archivo:
```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
Ahora tomemos solo los nombres de usuario del archivo. Donde `-F` especifica con base en que se separaran los campos. En este caso sera `:`. `{ print $1 }` indica imprimirr de salida el primer campo que coincida.

```bash
awk -F':' '{ print $1 }' /etc/passwd
```
Despues de ejecutar el comando anterior  se tendra la siguiente salida.
```
root
daemon
bin
sys
sync
```
Para mas detalles en como utilizar `awk`, revisa el siguiente [link](https://www.cyberciti.biz/faq/bash-scripting-using-awk).
### b. `cut`
Elimina secciones de cada linea de los archivos
*Ejemplo.txt*
```bash
red riding hood went to the park to play
```
*muestra me las columnas 2, 7 , y 9 con un espacio en blanco como separador*
```bash
cut -d " " -f2,7,9 Ejemplo.txt
```
```bash
riding park play
```

### c. `echo`
Despliega una linea de texto


*despliega "hola mundo"*
```bash
echo hola mundo
```
```bash
hola mundo
```

*despliega "hola mundo" con lineas nuevas entre palabras*
```bash
echo -ne "Hello\nWorld\n"
```
```bash
Hello
World
```

### d. `egrep`
Imprime las lineas que corresponda a un patron - Expresion extendida (alias para: 'grep -E')


*Ejemplo.txt*
```bash
Lorem ipsum
dolor sit amet, 
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```
*Despliega lineas que contengan "Lorem" o "dolor" en ellas.*
```bash
egrep '(Lorem|dolor)' Ejemplo.txt
or
grep -E '(Lorem|dolor)' Ejemplo.txt
```
```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### e. `fgrep`
Imprime lineas que correspondan a un patron - Correspondencia de patron FIJO (alias for: 'grep -F')

*Ejemplo.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor) 
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*Encuentra la cadena exacta '(Lorem|dolor)' en Ejemplo.txt*
```bash
fgrep '(Lorem|dolor)' Ejemplo.txt
or
grep -F '(Lorem|dolor)' Ejemplo.txt
```
```bash
foo (Lorem|dolor) 
```

### f. `fmt`
Formateador de texto simple y optimizado

*Ejemplo: Ejemplo.txt (1 linea)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```
*Entrega lineas de  Ejemplo.txt hasta 20 caracteres en total*
```bash
cat Ejemplo.txt | fmt -w 20
```
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### g. `grep`
Busca texto dentro de los archivos. Se puede utilizar grep para buscar lineas de texto que correspondan una o varias expresiones regulares y entrega como salida solo las lineas que corresponda.

```bash
grep pattern filename
```
Ejemplo:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
Tambien se puede forzar grep para que ignore mayusculas utilizando `-i`. `-r` puede ser utilizado para buscar todos los archivos en un directorio especificado, por ejemplo:
```bash
$ grep -r admin /etc/
```
Y `-w` se puede utilizar para buscar solo palabras. Para mas detalles de `grep` revisa el siguiente  [link](https://www.cyberciti.biz/faq/grep-in-bash).


### h. `nl`
Numero de lineas en archivos
*Ejemplo.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*show Ejemplo.txt with line numbers*
```bash
nl -s". " Ejemplo.txt 
```
```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`
Stream editor for filtering and transforming text

*Ejemplo.txt*
```bash
Hello This is a Test 1 2 3 4
``` 
*reemplaza todos los espacios con guiones*
```bash
sed 's/ /-/g' Ejemplo.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```
*reemplaza todos los digitos con "d"*
```bash
sed 's/[0-9]/d/g' Ejemplo.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`

Ordena lineas de archivos de texto

*Ejemplo.txt*
```bash
f
b
c
g
a
e
d
```

*Ordenar Ejemplo.txt*
```bash
sort Ejemplo.txt
```
```bash
a
b
c
d
e
f
g
```

*Ordena de manera aleatorio un archivo ordenadoEjemplo.txt*
```bash
sort Ejemplo.txt | sort -R
```
```bash
b
f
a
c
d
g
e
```

### k. `tr`
Reemplaza o elimina caracteres.

*Ejemplo.txt*
```bash
hola mundo Foo Bar Baz!
```
*toma todas las letras minusculas y las convierte en mayusculas *
```bash
cat Ejemplo.txt | tr 'a-z' 'A-Z' 
```
```bash
hola mundo FOO BAR BAZ!
```
*toma todos los espacios y los convierte en saltos de linea*
```bash
cat Ejemplo.txt | tr ' ' '\n'
```
```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`
Reporta o omite lineas repetidas

*Ejemplo.txt*
```bash
a
a
b
a
b
c
d
c
```

*muestra solo lineas unicas de Ejemplo.txt (primero necesitas ordenarlo, de otra manera no vera las coincidencias)*
```bash
sort Ejemplo.txt | uniq
```
```bash
a
b
c
d
```

*muestra los items unicos de cada linea y muestrar cuantas instancias encontro*
```bash
sort Ejemplo.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`
Obtiene cuantas lineas, palabras y caracteres hay en un archivo.
```bash
wc filename
```
Ejemplo:
```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```
Donde `7459` son lineas, `15915` son palabras y `398400` son caracteres.

## 1.3. Operaciones con Directorios

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
Te mueve de un directorio a otro, ejecutando lo siguiente
```bash
$ cd
```
te mueve al directorio home. Este comando acepta de manera opcional `dirname`, el cual te mueve a ese directorio.
```bash
cd dirname
```

### b. `mkdir`
Crea un nuevo directorio.  
```bash
mkdir dirname
```
Puedes utilizar este comando para crear multiples directorios al mismo tiempo en el directorio actual.
```bash
mkdir 1stDirectory 2ndDirectory 3rdDirectory
```
Tambien puedes utilizarlo para crear directorios padre al mismo tiempo. Por ejemplo, si quieres un directorio llamada 'project1' en otro subdirectorio como '/samples/bash/projects/', puedes ejecutar:

```bash 
mkdir /samples/bash/projects/project1
```
Si alguno de estos directorios no existe, se crearan tambien.
### c. `pwd`
Te indica en que directorio te encuentras.
```bash
pwd
```

## 1.4. SSH, Informacion del Sistema y Operaciones de Red

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>   
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
   </tr>
</table>

### a. `bg`
Lista trabajos detenidos o en background; reinicia un trabajo en background.
### b. `cal`
Muestra el mes del calendario.

### c. `date`
Muestra la fecha y hora actual.

### d. `df`
Muestra el uso del disco.

### e. `dig`
Obtiene informacion DNS para un dominio.
```bash
dig domain
```

### f. `du`
Muestra el uso del disco de archivos y directorios. Para mas informacion en este comando revisa este [link](http://www.linfo.org/du.html)
```bash
du [option] [filename|directory]
```
Opciones:
- `-h` (legile para humanos) Despliega salida en kilobytes (K), megabytes (M) y gigabytes (G).
- `-s` (suprimir o sumarizar) Despliega el spacio total en disco de un directorio y suprime el reporte para los subdirectorios. 

Ejemplo:
```bash
du -sh pictures
1.4M pictures
```

### g. `fg`
Obtiene el trabajo mas reciente en el foreground.


### h. `finger`
Despliega informacion acerca del usuario.
```bash
finger username
```
### i. `jobs`
Lista los trabajos corriendo en el background, indicando el numero de trabajo.

### j. `last`
Lista los ultimos logins del usuario especificado.
```bash
last yourUsername
```

### k. `man`
Muestra el manual para un comando especificado.
```bash
man command
```

### l. `passwd`
Permite al usuario logueado cambiar su password.
### m. `ping`
Ejecuta un ping a un host y entrega los resultados como salida.
```bash
ping host
```

### n. `ps`
Lista tus procesos.
```bash
ps -u yourusername
```
Utilice las banderas ef, e para mostrar todos los procesos y f para una lista completa.
```bash
ps -ef
```

### o. `quota`
Muestra cual es la cuota de disco.
 
```bash
quota -v
```

### p. `scp`
Transiferer archivos entre un host local y un host remoto o entre dos host remotos.

*copiar de un host local a un host remoto*
```bash
scp source_file user@host:directory/target_file
```
*copiar de un host remoto a un host local*
```bash
scp user@host:directory/source_file target_file
scp -r user@host:directory/source_folder target_folder
```
Este comando tambien acepta la opcion `-P` que se puede utilizar para conectarse a un puerto especifico. 
```bash
scp -P port user@host:directory/source_file target_file
```

### q. `ssh`
ssh (cliente SSH) es un prrograma para iniciar sesion y ejecutar comandos en una maquina remota.
```bash
ssh user@host
```
Este comando tambien acepta la opcion `-P` que se puede utilizar para conectarse a un puerto especifico.  
```bash
ssh -p port user@host
```

### r. `top`
Despliega los procesos activos al momento.

### s. `uname`
Muestra informacion del kernel.
```bash
uname -a
```

### t. `uptime`
Muestra el tiempo que el sistema ha estado arriba.

### u. `w`
Despliega quien esta en linea.

### v. `wget`
Descarga un archivo  
```bash
wget file
```

### w. `whoami`
Regresa el nombre del usuario que tiene la sesion.

### x. `whois`
Obtiene informacion whois para el dominio.
```bash
whois domain
```

## 1.5. Operaciones de Monitoreo de Procesos

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
Elimina (termina) los procesos con el ID proporcionado.
```bash
kill PID
```

### b. `killall`
Elimina todos los procesos con el nombre proporcionado
```bash
killall processname
```

### c. &
El simbolo `&` le indica al comando que se ejcuta como un proceso en background en una subshell.
```bash
command &
```

### d. `nohup`
nohup significa "No hang up" (No colgar). Esto permite ejecutarr comandos/procesos o shell scripts para que pueda continuar corriendo en background aun cuando se sale de una shell.
```bash
nohup command
```
Combinalo con `&` para crear un proceso en background.
```bash
nohup command &
```

# 2. Programacion Basica de Shell

Las primera linea que escribiras en un archivo de bash script es llamado `shebang`. Esta linea en cualquier script determina la habilidad del script para ser ejecutado como un ejecutable independiente sin tener que teclear sh, bash, python, php, etcetera en la termina.

```bash
#!/usr/bin/env bash
```

## 2.1. Variables

Crear variables en bash es similar a otros lenguajes. No existen los tipos de datos. Una variable en bash puede contener un numero, un caracter, una cadena de caracteres, etc. No tienes que declarar una variable, solo asignarle un valor creara la variable.

Ejemplo:
```bash
str="hola mundo"
```
La linea anterior crea una variable `str` y asigna "hola mundo" a esta. El valor de la variable es obtenido añadiendo el `$` al inicio de la variable.

Ejemplo:
```bash
echo $str   # hola mundo
```
## 2.2. Arreglos
Como en otros lenguajes, bash tambien tiene arreglos. Un arreglo es una variable que contiene multiples valores. No hay un limite maximo en el tamaño de un arreglo. Los arreglos en bash son base cero. El primer elemento es indexado con elemento 0.Hay varias maneras de crear arreglos en bash las cuales se muestran a continuacion.

Examples:
```bash
array[0]=val
array[1]=val
array[2]=val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```
Para mostrar el valor especifico de un indice se utiliza la siguiente sintaxis:

```bash
${array[i]}     # donde i es el indice
```

Si no se proporciona un indice, se asume el elemento 0. Para encontrar cuandos valores hay en el arreglo utilice la siguiente sintaxis:

```bash
${#array[@]}
```

Bash tambien tiene soporte para condiciones ternarias. Revisa algunos de los siguientes ejemplos.
```bash
${varname:-word}    # if varname exists and isn't null, return its value; otherwise return word
${varname:=word}    # if varname exists and isn't null, return its value; otherwise set it word and then return its value
${varname:+word}    # if varname exists and isn't null, return word; otherwise return null
${varname:offset:length}    # performs substring expansion. It returns the substring of $varname starting at offset and up to length characters
```

## 2.3 Substituir Cadenas

Revisa algunos ejemplos de sintaxis para como manipular cadenas

```bash
${variable#pattern}         # si el patron corresponde al inicio del valor la variable, elimina la parte mas corta que corresponda y regresa el resto 
${variable##pattern}        # si el patron corresponde a el inicio del valor de la variable, elimina la parte mas larga y regresa el resto 
${variable%pattern}         # si el patron corresponde a el final del valor de la variable, elimina la parte mas corta y regresa el resto 
${variable%%pattern}        # si el patron corresponde a el final del valor de la variable, elimina la parte mas larga y regresa el resto 
${variable/pattern/string}  # el patron mas largo que corresponda en la variable es reemplazado por string. Solo la primera coincidencia es reemplazada.
${variable//pattern/string} # el patron mas largo que corresponda en la variable es reemplazado por string. Todas las coincidencias son reemplazadas.
${#varname}     # regresa el largo del valor de la variable como un caracter de cadena 
```

## 2.4. Funciones

Como en casi todos los lenguajes de prograrmacion, se pueden utilizar funciones para agrupar piezas de codigo de una manera mas logica o para practicar el divino arte de la recursion. Declarar una funcion solo consiste en escribir function mi_funcion { mi_codigo }. Llamar a la funcion es como llamar a cualquier otro programa, solo hay que escribir su nombre.

```bash
function nombre() {
    comandos de shell
}
```

Ejemplo:
```bash
#!/bin/bash
function hola {
   echo mundo!
}
hola

function say {
    echo $1
}
say "hola mundo!"
```

Cuando ejecutas el ejemplo anterior la funcion `hola` enviara como salida "mundo!". Las funciones anteriores `hola` y `say` son identicas. La principal diferencia es que la funcion `say`. Esta funcion, imprime el primer argumento que recibe. Argumentos dentro las funciones son tratados en la misma manera que los argumentos dinamicos que se dan al script.

## 2.5. Condicionales

Las instrucciones condicionales en bash son similares a otros lenguajes de programacion. Las condiciones tienen muchas formas, como por ejemplo la forma mas basica es `if` expresion `then` instrucciones, donde instrucciones solo se ejecutan si la expresion es verdadera.

```bash
if [ expresion ]; then
    se ejecutara solo si la expresion es verdadera    
else
    se ejecutara solo si la expresion es falsa
fi
```
En ocasiones, si las condiciones se vuelven confusas, se pueden escribir las mismas utilizando `case statements`.

```bash
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

Ejemplos de expresiones:

```bash
statement1 && statement2  # ambas condiciones son verdaderas
statement1 || statement2  # por lo menos una de las condiciones son verdaderas

str1=str2       # str1 es igual a str2
str1!=str2      # str1 no es igual a str2
str1<str2       # str1 es menor que str2
str1>str2       # str1 es mayor que str2
-n str1         # str1 no es nulo (tiene una longitud mayor que 0)
-z str1         # str1 es nulo (tiene una longitud de 0)

-a file         # el archivo existe
-d file         # el archivo existe y es un directorio
-e file         # el archivo existe, mismo funcionamiento que -a
-f file         # el archivo existe y es un archivo normal (por ejemplo, no es un directorio o un tipo de archivo especial) 
-r file         # se tiene permiso de lectura
-s file         # el archivo existe y NO esta vacio
-w file         # se tiene permiso de escritura
-x file         # se tiene permisos para ejecutar el archivo o de busqueda si es un directorio
-N file         # el archivo fue modificado desde la ultima lectura
-O file         # eres el dueño del archivo
-G file         # el ID del grupo del archivo es igual que el de tu usuario (o en alguno de tus grupos si tienes varios)

file1 -nt file2     # file1 es mas nuevo que file2
file1 -ot file2     # file1 es mas viejo que file2

-lt     # menor que
-le     # menor o igual que
-eq     # igual
-ge     # mayor o igual que
-gt     # mayor que
-ne     # no es igual
```

## 2.6. Ciclos

Hay tres tipos de ciclos en bash. `for`, `while` y `until`.


Diferentes sintaxis de `for` :
```bash
for x := 1 to 10 do
begin
  statements
end

for name [in list]
do
  statements that can use $name
done

for (( initialisation ; ending condition ; update ))
do
  statements...
done
```

Sintaxis de `while` :
```bash
while condition; do
  statements
done
```

Sintaxis de `until` :
```bash
until condition; do
  statements
done
```

# 3. Trucos

## Establecer un alias

Ejecutar `nano ~/.bash_profile` y agregar la siguiente linea:

```bash
alias dockerlogin='ssh www-data@adnan.local -p2222'  # agregar tu alias en .bash_profile
```

## Para rapidamente movers a un directorio especifico

Ejecutar `nano ~/.bashrc` y agregar la siguiente linea:

```bash
export hotellogs="/workspace/hotel-api/storage/logs"
```
Ahora puedes utilizar el path guardado:

```bash
source ~/.bashrc
cd $hotellogs
```

## Re-ejecutar el comando anterior

Esto se remonta a los dias cuando no se podia confiar en que los teclados tengan una tecla de flecha "hacia arriba", pero puede aun ser util

Para ejecutar el ultimo comando en su historia.
```bash
!!
```
Un error comun es el olvidar utilizar `sudo` como prefijo de un comando que requiere privilegios parar su ejecucion. En lugarr de teclear todo el comando de nuevo, puedes usar:

```bash
sudo !!
```
Esto cambiara  `mkdir somedir` en `sudo mkdir somedir`.
## Trampas de salida

Haga sus scrips de bash mas robustos ejecutando de manera regular limpieza.

```bash
function finish {
  # your cleanup here. e.g. kill any forked processes
  jobs -p | xargs kill
}
trap finish EXIT
```

## Guardar variables de ambiente

Cuando se ejecuta `export FOO = BAR`, la variable de ambiente solo se exporta en la shell actual y todos sus hijos, para persistirla en el futuro se puede simplemente agregar en el archivo `~/.bash_profile` el comando para exportar la variable

```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Acceder a tus scripts

Puedes facilmente  utilizar tus scripts creando un folder bin en tu directorio home utilizando `mkdir ~/bin`, de esta manera todos los scripts que se guarden en este directorio pueden ser utilizados desde cualquier directorio.

Si esto no funciona, prueba agregando el siguiente codto en tu archivo `~/.bash_profile` y despues ejecuta `source ~/.bash_profile`.

```bash
# Configurar PATH para que incluya el directorio privado bin del usuario si existe
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

# 4. Depuracion

Puedes facilmente depurar scrips de bash enviando diferentes opciones a el comando `bash`. Por ejemplo `-n` no ejecutara el comando y solo revisara errores de sintaxis. `-v` realiza un echo del comando antes de ejecutarlo. `-x` realiza un echo del comando despues de procesarlo. 
ß

```bash
bash -n nombredelscript
bash -v nombredelscript
bash -x nombredelscript
```

## Contribuciones

- Reportar problemas [Como hacerlo](https://help.github.com/articles/creating-an-issue/)
- Abril solicitudes de cambios con mejoras [Como hacerlo](https://help.github.com/articles/about-pull-requests/)
- Compartir informacion

## Traducciones
- [Ingles | Original](https://github.com/Idnan/bash-guide)
- [Chino | 简体中文](https://github.com/vuuihc/bash-guide)
- [Turco | Türkçe](https://github.com/omergulen/bash-guide)
- [Japones | 日本語](https://github.com/itooww/bash-guide)

## Licencia

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
