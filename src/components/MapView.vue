<template>
    <div>
      <div ref="map" class="map"></div>
    </div>
  </template>
  
  <script>
  import mapboxgl from 'mapbox-gl';
  import 'mapbox-gl/dist/mapbox-gl.css';
  
  export default {
    mounted() {
      mapboxgl.accessToken = 'pk.eyJ1Ijoia291bmRpbnlhMnk1IiwiYSI6ImNsbXNocnhodzA1NnIyaW1mcHNydzh5M3AifQ.LQ8QgKlRY9dpdkBtKn67kA';
      const map = new mapboxgl.Map({
        container: this.$refs.map,
        style: 'mapbox://styles/mapbox/streets-v11',
        center: [-74.5, 40], // Default center coordinates
        zoom: 9,
      });
  
      // Default static marker coordinates
      const staticMarkerCoords = [-74.5, 40];
  
      // Add a static marker to the map
      new mapboxgl.Marker().setLngLat(staticMarkerCoords).addTo(map);
    },
  };
  </script>
  
  <style scoped>
  .map {
    height: 400px;
  }
  </style>