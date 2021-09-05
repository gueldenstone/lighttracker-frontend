<template>
  <div id="mapContainer" class="basemap"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";

export default {
  name: "BaseMap",
  data() {
    return {
      accessToken: process.env.VUE_APP_MAPBOX_ACCESS_TOKEN,
    };
  },
  mounted() {
    mapboxgl.accessToken = this.accessToken;

		new mapboxgl.Map({
			container: 'mapContainer', // container ID
			style: 'mapbox://styles/mapbox/streets-v11', // style URL
			center: [-74.5, 40], // starting position [lng, lat]
			zoom: 9 // starting zoom
		});
  },
};
</script>

<style>
.basemap {
  width: 100%;
  height: 100%;
}
</style>