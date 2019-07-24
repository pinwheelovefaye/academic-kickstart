+++
# Contact widget.
widget = "contact"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 130  # Order that this section will appear.

title = "Contact"
subtitle = ""

# Automatically link email and phone?
autolink = true

# Email form provider
#   0: Disable email form
#   1: Netlify (requires that the site is hosted by Netlify)
#   2: formspree.io
email_form = 0
+++

<div id="map" style="width:100%;height:400px;background:yellow"></div>

<script>
function myMap() {
    var uluru = {lat: 22.309743, lng: 39.104718}; 
    var map = new google.maps.Map(document.getElementById("map"), { 
      zoom: 15, 
      center: uluru 
    }); 
    var marker = new google.maps.Marker({ 
      position: uluru, 
      map: map 
    }); 
}
</script>
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDiwnkgNPu49OLPYdSiYb4OB35X6K1Smlc&callback=myMap"></script>

