Convertir de .xls a .csv en Libreoffice desde terminal en GNU/Linux
==================================

Fecha: 2017-08-09 14:10
Autor: Osvaldo
Categorías: LibreOffice, Debian, Datos Abiertos

Hace unos días [Guabyboy](https://twitter.com/guabyboy) y un servidor, mientras disfrutabamos de un café, hablabamos de [Software Libre](https://es.wikipedia.org/wiki/Software_libre) (para variar): como hacer calculos estadisticos con [PSPP](https://www.gnu.org/software/pspp/). Para ello usamos [datos abiertos](https://es.wikipedia.org/wiki/Datos_abiertos) que propcorciona el gobierno, y nos encontramos que los porporcionan en .xls, y no en [.CSV](https://es.wikipedia.org/wiki/CSV) que sería lo ideal.

El archivo en cuestión tenía miles de registros (filas y columnas) y al abrirlo en [Libreoffice](http://www.libreoffice.org/) para convertirlo a CSV se tardaba mucho, y se tardaba mucho más después de aplicar la orden "Guardar como..." se tardaba aún más... en eso recordé que en [LibreOffice también se puede usar la terminal](https://salazarysanchez.github.io/entradas/2014-04-28-Convertir-odt-ods-en-pdf-con-LibreOffice-desde-terminal.html), por lo que leí la ayuda de LibreOffice desde terminal de mi [Debian](http://www.debian.org/) y encontré que usando:

<pre><code>$ libreofficeX.X --headless --convert-to csv Archivo_con_miles_de datos.xls</code></pre>

<pre><code>donde X.X es la versión de LibreOffice instalada</code></pre>

se puede crear el respectivo archivo .csv en un tiempo mucho menor.

Espero les sea de utilidad como lo fue para nosotros :D
