+++
widget = "blank"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = false  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 36  # Order that this section will appear.

title = "Collaborators"
subtitle = ""

[design.spacing]
# Customize the section spacing. Order is top, right, bottom, left.
padding = ["20px", "0", "20px", "0"]

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css"
integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A=="
crossorigin=""/>

<!-- Make sure you put this AFTER Leaflet's CSS -->
 <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"
   integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA=="
   crossorigin=""></script>
   
+++

_Collaborators are listed in alphabetical order of last names._


| Name              | Institution | Department/Divison |
| ------------------| ------------|------------------- |
| [Leontine Alkema](https://leontinealkema.github.io/alkema_lab/) | UMass Amherst | Department of Biostatistics and Epidemiology, School of Public Health & Health Sciences |
| [Alex R. Cook](https://sph.nus.edu.sg/faculty-directory/cook-alex-richard/) | NUS | Biostatistics and Modelling Domain, Saw Swee Hock School of Public Health |
| [Patrick Gerland](http://www.researchgate.net/profile/Patrick_Gerland) | UN | Population Division, Department of Economic and Social Affairs |
| [Christophe Z. Guilmoto](http://www.demographie.net/) | Université de Paris | Centre Population et Développement (CEPED); Institut de recherche pour le développement (IRD) |
| Lucia Hug | UNICEF | Division of Data, Research, and Policy |
| [Samir KC](http://www.wittgensteincentre.org/en/staff/member/kc.htm) | Shanghai University; International Institute for Applied Systems Analysis (IIASA) | Asian Demographic Research Institute (ADRI); Wittgenstein Centre for Demography |
| [Bruno Masquelier](https://uclouvain.be/fr/repertoires/bruno.masquelier) | Université catholique de Louvain | Center for Demographic Research |
| [Hernando Ombao](https://cemse.kaust.edu.sa/biostats/people/person/hernando-ombao) | KAUST | Statistics Program |
| [Jon Pedersen](https://fafo.no/index.php/ansatte?controller=renderlayout&task=show&item_id=4722&layout=utskrift&tmpl=component) | FAFO | |
| [Danzhen You](https://scholar.google.com/citations?user=9-z_XD4AAAAJ&hl=en) | UNICEF | Division of Data, Research, and Policy |


<div id="mapid"></div>
var mymap = L.map('mapid').setView([51.505, -0.09], 13);
L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
    attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
    maxZoom: 18,
    id: 'mapbox/streets-v11',
    tileSize: 512,
    zoomOffset: -1,
    accessToken: 'your.mapbox.access.token'
}).addTo(mymap);