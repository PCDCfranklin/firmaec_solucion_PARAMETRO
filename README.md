# firmaec_solucion_PARAMETRO
Mi solución al "Error: Se debe enviar un parámetro"


--------------------------------PREAMBULO---------------------------------------
<br>
En algunos sistemas operativos GNU/Linux(Fedora, ubuntu, Linux mint, otros), el script de instalación de FIRMAEC tomado de: https://www.firmadigital.gob.ec/descargar-firmaec/ 
implementa las dependencias en los directorios /usr/share/xxxx. 


<br>
Si embargo, al ejecutar FIRMAEC a través de la consola, se han evidenciado errores con un mensaje relacionado con java en el que se menciona "ERROR: SE DEBE ENVIAR UN PARAMETRO"


<br>
El problema se encuentra en que dentro del entorno linux se genera un lanzador FIRMAEC mal direccionado, es decir apunta al fichero /usr/bin/firmaec cuando el archivo ejecutable se encuentra ubicado en: /usr/share/firmaec/firmador y depende del parametro %u para ejecutarlo.

<br>
--------------------------------SOLUCION---------------------------------------
<br>

<br>
La solucion, para usuarios entendidos en el entorno linux seria abrir una terminal y ejecutar "firmador" en lugar de "firmaec" con lo que se desplegará el entorno gráfico del firmador que anteriormente no lo hacía. 

<br>
Para el caso de usuarios finales, es necesario corregir o crear un lanzador en el escritorio del usuario. Para ello vamos a realizar los siguientes pasos:
<br>
$ sudo apt install git
<br>
$ cd /home/USUARIO/ESCRITORIO #acceder al escritorio del usuario al que se le va a habilitar el entorno grafico del firmador
<br>
$ git clone https://github.com/PCDCfranklin/firmaec_solucion_PARAMETRO.git
<br>
$ cp /firmaec_solucion_PARAMETROS/firmador.desktop ~/Escritorio/
<br>
$ rm -Rf firmaec_solucion_PARAMETROS/
<br>
$ chmod 755 firmador.desktop
<br><br>

AHORA ES POSIBLE EJECUTAR EL FIRMADOR CON EL LANZADOR CREADO EN EL ESCRITORIO
