# Wizualizacje KFnrD

Wizualizacje z danych [Krajowego Funduszu na rzecz Dzieci](http://fundusz.org/) - organizacji pożytku publicznego pomagającej zdolnej młodzieży.

* [Mapa uczestników i ich zainteresowań w latach 1997-2013](http://stared.github.io/kfnrd_viz/mapa.html)
* Inne nadejdą

Autor: [Piotr Migdał](http://migdal.wikidot.com/), 2014, [open source: MIT](http://en.wikipedia.org/wiki/MIT_License).

Podziękowania dla Łukasza Partyki za umożliwienie (dane!) i pomoc oraz [Dorki Budacz](http://dorkabudacz.waw.pl/) za uwagi graficzne.

![Mapa uczestników i zainteresowań w latach 1997-2013](screenshot.png)

## Źródła

* Uczestnicy, dziedziny: [Krajowy Fundusz na rzecz Dzieci](http://fundusz.org/).
  * Tylko jedno główne zainteresowanie uczestnika, skategoryzowane w ramach szerszych dziedzin.
* Wizualizacja w bibliotece [D3.js](http://d3js.org/) i [Topojson](https://github.com/mbostock/topojson/wiki).
* Geolokalizacje miast: [Google Geocoding API](https://developers.google.com/maps/documentation/geocoding/).
* Mapa Polski:
  * Dane z [Global Administrative Areas (GADM)](http://www.gadm.org/), plik shapefile `POL_adm1.shp` ([POL_adm.zip](http://biogeo.ucdavis.edu/data/gadm2/shp/POL_adm.zip)).
  * Następnie przetworzone na Topojson, zgodnie z instrukcją [Interactive Map with d3.js](http://www.tnoda.com/blog/2013-12-07).

Kod:

    $ ogr2ogr -f GeoJSON -simplify 0.01 poland_woj.json POL_adm1.shp
    $ topojson -o poland_woj.topo.json poland_woj.json

## Znane problemy

* Zaniżona liczba stypendystów baletowych (powinno być ~20 na rok).
* Niektóre miejscowości mogą występować kilkukrotnie na skutek.różnic w pisowni.
* Niektóre miejscowośc mogą być źle zlokalizowane.

## Uwagi

Też chcesz umieć taką stworzyć? Daj nura w [mój wstęp](http://smarterpoland.pl/index.php/2014/06/metawstep-do-wizualizacji-danych-w-d3-js/).

Żadna metoda geolokalizacji nie jest w 100% skuteczna. Każde dane mogą zawierać śladowe ilości błędów, a także orzechów arachidowych. Gdzie się przetwarzający dane spieszy, tam się entropia cieszy.
Produkt do użytku na własną odpowiedzialność.
