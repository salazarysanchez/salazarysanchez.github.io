Imagen estereoscópica del asteroide DonaldJohanson
===========

Fecha: 2025-04-23 16:00
Autor: Osvaldo
Categorías: Astronomía, ffmpeg, Asteroide, Lucy, DonaldJohanson

En estos días la sonda [Lucy](https://es.wikipedia.org/wiki/Lucy_(sonda_espacial)) llegó al asteroide [DonaldJohanson](https://en.wikipedia.org/wiki/52246_Donaldjohanson).

<!-- break -->

Brian May [invitó](https://www.instagram.com/p/DIuNdSFsTAk/) a sus seguidores a usar una versión liberada por la NASA y hacer una imagen estereoscópica de la misma.

Usando [ffmpeg](https://ffmpeg.org/) realicé varias pruebas, pero solo dos me gustaron... y solo una me permitió instagram [subirlo](https://www.instagram.com/p/DIznZZbOC7D/).

Una fue:

<pre><code>
ffmpeg -i DJ.mp4 -vf stereo3d=al:sbsl test1.mp4
</code></pre>

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/ljtGwb9uIHA?si=zi6S9BdaElnvIGL2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</center>

<br />

Y la segunda fue:

<pre><code>
ffmpeg -i DJ.mp4 -vf stereo3d=sbs2l:arch test2.mp4
</code></pre>

... que se puede ver [aquí](https://www.youtube.com/shorts/p2SQLFwZsXE)

<br />


