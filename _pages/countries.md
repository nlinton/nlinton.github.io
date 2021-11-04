---
layout: archive
title: "Countries visited"
permalink: /countries/
author_profile: true
---

<script src="https://www.amcharts.com/lib/3/ammap.js" type="text/javascript"></script>
<script src="https://www.amcharts.com/lib/3/maps/js/worldHigh.js" type="text/javascript"></script>
<script src="https://www.amcharts.com/lib/3/themes/dark.js" type="text/javascript"></script>
<div id="mapdiv" style="width: 1000px; height: 450px;"></div
<!--- courtesy of amcharts.com -->
<script type="text/javascript">
var map = AmCharts.makeChart("mapdiv",{
type: "map",
theme: "dark",
projection: "mercator",
panEventsEnabled : true,
backgroundColor : "#535364",
backgroundAlpha : 1,
zoomControl: {
zoomControlEnabled : true
},
dataProvider : {
map : "worldHigh",
getAreasFromMap : true,
areas :
[
	{
		"id": "DE", <!-- Germany -->
		"showAsSelected": true
	}
  {
		"id": "Dk", <!-- Denmark -->
		"showAsSelected": true
	}
  {
		"id": "FI", <!-- Finland -->
		"showAsSelected": true
	}
  {
		"id": "FR", <!-- France -->
		"showAsSelected": true
	}
  {
    "id": "GR", <!-- Greece -->
    "showAsSelected": true
  }
  {
  	"id": "IE", <!-- Ireland -->
  	"showAsSelected": true
  }
  {
  	"id": "IS", <!-- Iceland -->
  	"showAsSelected": true
  }
  {
    "id": "IT", <!-- Italy -->
    "showAsSelected": true
  }
  {
    "id": "JA", <!-- Japan -->
    "showAsSelected": true
  }
]
},
areasSettings : {
autoZoom : true,
color : "#B4B4B7",
colorSolid : "#84ADE9",
selectedColor : "#84ADE9",
outlineColor : "#666666",
rollOverColor : "#9EC2F7",
rollOverOutlineColor : "#000000"
}
});
</script>
