jQuery(document).ready(function($) {
	
	/**
	 * Google maps widgets 
	 */
	$('.gmap').each(function() {
		
		var $gmap = $(this);
		var zoom = 2;
		var lat = 0;
		var lng = 0;
		var lt_map_type = $gmap.attr('data-type');

		switch($gmap.attr('data-type')) {
			case "ROADMAP":
			    lt_map_type = google.maps.MapTypeId.ROADMAP;
			    break;
			case "SATELLITE":
			    lt_map_type = google.maps.MapTypeId.SATELLITE;
			    break;
			case "HYBRID":
			    lt_map_type = google.maps.MapTypeId.HYBRID;
			    break;
			case "TERRAIN":
			    lt_map_type = google.maps.MapTypeId.TERRAIN;
			    break;
			default:
			    lt_map_type = google.maps.MapTypeId.ROADMAP;
		}

		if($gmap.attr('data-coords')) {
			var parts = $gmap.attr('data-coords').split(',');
			
			if(typeof parts[0] != 'undefined') {
				lat = parts[0];
			}
			
			if(typeof parts[1] != 'undefined') {
				lng = parts[1];
			}
			
			if(typeof parts[2] != 'undefined') {
				zoom = parseInt(parts[2], 10);
			}
			
		}
	
		google.maps.event.addDomListener(window, 'load', init);

		function init() {

			var mapOptions = {
				mapTypeId: lt_map_type,
				scrollwheel : false,
				zoom : zoom,
				center : new google.maps.LatLng(lat, lng),
				styles : [{
					featureType : "landscape",
					stylers : [{
						saturation : -100
					}, {
						lightness : 65
					}, {
						visibility : "on"
					}]
				}, {
					featureType : "poi",
					stylers : [{
						saturation : -100
					}, {
						lightness : 51
					}, {
						visibility : "simplified"
					}]
				}, {
					featureType : "road.highway",
					stylers : [{
						saturation : -100
					}, {
						visibility : "simplified"
					}]
				}, {
					featureType : "road.arterial",
					stylers : [{
						saturation : -100
					}, {
						lightness : 30
					}, {
						visibility : "on"
					}]
				}, {
					featureType : "road.local",
					stylers : [{
						saturation : -100
					}, {
						lightness : 40
					}, {
						visibility : "on"
					}]
				}, {
					featureType : "transit",
					stylers : [{
						saturation : -100
					}, {
						visibility : "simplified"
					}]
				}, {
					featureType : "administrative.province",
					stylers : [{
						visibility : "off"
					}]/**/},{featureType:"administrative.locality",stylers:[{visibility:"off"}]},{featureType:"administrative.neighborhood",stylers:[{visibility:"on"}]/**/
				}, {
					featureType : "water",
					elementType : "labels",
					stylers : [{
						visibility : "on"
					}, {
						lightness : -25
					}, {
						saturation : -100
					}]
				}, {
					featureType : "water",
					elementType : "geometry",
					stylers : [{
						hue : "#ffff00"
					}, {
						lightness : -25
					}, {
						saturation : -97
					}]
				}]
				//styles: [{featureType:'water',elementType:'geometry',stylers:[{color:'#a2daf2'}]},{featureType:'landscape.man_made',elementType:'geometry',stylers:[{color:'#f7f1df'}]},{featureType:'landscape.natural',elementType:'geometry',stylers:[{color:'#d0e3b4'}]},{featureType:'landscape.natural.terrain',elementType:'geometry',stylers:[{visibility:'off'}]},{featureType:'poi.park',elementType:'geometry',stylers:[{color:'#bde6ab'}]},{featureType:'poi',elementType:'labels',stylers:[{visibility:'off'}]},{featureType:'poi.medical',elementType:'geometry',stylers:[{color:'#fbd3da'}]},{featureType:'poi.business',stylers:[{visibility:'off'}]},{featureType:'road',elementType:'geometry.stroke',stylers:[{visibility:'off'}]},{featureType:'road',elementType:'labels',stylers:[{visibility:'off'}]},{featureType:'road.highway',elementType:'geometry.fill',stylers:[{color:'#ffe15f'}]},{featureType:'road.highway',elementType:'geometry.stroke',stylers:[{color:'#efd151'}]},{featureType:'road.arterial',elementType:'geometry.fill',stylers:[{color:'#ffffff'}]},{featureType:'road.local',elementType:'geometry.fill',stylers:[{color:'black'}]},{featureType:'transit.station.airport',elementType:'geometry.fill',stylers:[{color:'#cfb2db'}]}]
			};
			/*
			 var contentString = '<div id="content">'+
			 '<p>Yup, we are here!</p></div>';
			 var infowindow = new google.maps.InfoWindow({
			 content: contentString
			 });
			 */
			//var mapElement = document.getElementById('gmap');
			var map = new google.maps.Map($gmap[0], mapOptions);
			var image = $gmap.attr('data-marker');
			var myLatLng = new google.maps.LatLng(lat, lng);
			var marker = new google.maps.Marker({
				position : myLatLng,
				map : map,
				icon : image,
				title : 'Hello World!'
			});

			// google.maps.event.addListener(marker, 'click', function() {
				// infowindow.open(map, marker);
			// });
		
		}

	});
});
