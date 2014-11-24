Convertir odt/ods en pdf con LibreOffice desde terminal
==================================

Fecha: 2014-04-28 02:48
Autor: Osvaldo
Categorías: LibreOffice, Debian

En [Libreoffice](http://www.libreoffice.org/), desde antes que lo implementaran en Microsoft Office, se puede guardar el documento de trabajo en formato pdf (sigla del inglés portable document format) con solo presionar un icono.

Ayer me surgió la pregunta: _"¿Se podrá desde terminal hacer lo mismo?"_. La lógica apuntaba a que si se podía.

<!-- break -->

Buscando en la terminal, escribí el clásico comando _man_ en la terminal de mi [Debian](http://www.debian.org/) (donde X.X es la versión de LibreOffice instalada):

<pre><code>$ man libreofficeX.X</code></pre>

con lo que obtuve:

<pre><code>No manual entry for libreofficeX.X
See 'man 7 undocumented' for help when manual pages are not available.</code></pre>

La lógica me indicó buscar la ayuda, y como no la obtuve por _man_ lo intenté con el siguiente comando:

<pre><code>$ libreofficeX.X -h</code></pre>

con lo que obtuve:

<pre><code>LibreOffice X.X 89ea49ddacd9aa532507cbf654f2bb22b1

Usage: soffice [options] [documents...]

Options:
- -minimized keep startup bitmap minimized.
- -invisible no startup screen, no default document and no UI.
- -norestore suppress restart/restore after fatal errors.
- -quickstart starts the quickstart service
- -nologo don\'t show startup screen.
- -nolockcheck  don\'t check for remote instances using the installation
- -nodefault don\'t start with an empty document
- -headless like invisible but no userinteraction at all.
- -help/-h/-? show this message and exit.
- -version display the version information.
- -writer create new text document.
- -calc create new spreadsheet document.
- -draw create new drawing.
- -impress create new presentation.
- -base create new database.
- -math create new formula.
- -global create new global document.
- -web create new HTML document.
-o open documents regardless whether they are templates or not.
-n always open documents as new files (use as template).

- -display &lt;display&gt;
Specify X-Display to use in Unix/X11 versions.
-p &lt;documents...&gt;
print the specified documents on the default printer.
- -pt &lt;printer&gt; &lt;documents...&gt;
print the specified documents on the specified printer.
- -view &lt;documents...&gt;
open the specified documents in viewer-(readonly-)mode.
- -show &lt;presentation&gt;
open the specified presentation and start it immediately
- -accept=&lt;accept-string&gt;
Specify an UNO connect-string to create an UNO acceptor through which
other programs can connect to access the API
- -unaccept=&lt;accept-string&gt;
Close an acceptor that was created with --accept=&lt;accept-string&gt;
Use --unnaccept=all to close all open acceptors
- -infilter=&lt;filter&gt;
Force an input filter type if possible
Eg. --infilter=\"Calc Office Open XML\"
- -convert-to output_file_extension[:output_filter_name] [- -outdir output_dir] files
Batch convert files.
If - -outdir is not specified then current working dir is used as output_dir.
Eg. - -convert-to pdf *.doc
- -convert-to pdf:writer_pdf_Export - -outdir /home/user *.doc
- -print-to-file [-printer-name printer_name] [- -outdir output_dir] files
Batch print files to file.
If - -outdir is not specified then current working dir is used as output_dir.
Eg. - -print-to-file *.doc
- -print-to-file - -printer-name nasty_lowres_printer - -outdir /home/user *.doc
- -pidfile file
Store soffice.bin pid to file.

Remaining arguments will be treated as filenames or URLs of documents to open.</code></pre>

Leyendo a detalle lo anterior, use lo siguiente:

<pre><code>$ libreofficeX.X - -headless - -convert-to pdf "Propuesta trabajo.odt"</code></pre>

Con lo que obtuve un documento _Propuesta trabajo.pdf_ de un archivo creado con writer. Buen resultado obtuve al convertir una hoja de calculo a pdf con:

<pre><code>$ libreofficeX.X - -headless - -convert-to pdf "Presupuesto.ods"</code></pre>

No tuve ningun problema en convertir a pdf archivos con extensión .doc, .xls, .docx y .xlsx

Espero les sea de utilidad como lo fue para mi :D
