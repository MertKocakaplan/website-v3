<template>
  <div id="app">
    <MapComponent @map-loaded="handleMapLoaded" />
    <div v-if="!mapLoaded">Harita yükleniyor...</div>
  </div>
</template>

<script>
import MapComponent from './components/MapComponent.vue'

export default {
  name: 'App',
  components: {
    MapComponent
  },
  data() {
    return {
      mapLoaded: false
    };
  },
  methods: {
    handleMapLoaded(status) {
      this.mapLoaded = status;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.map-container .map {
  height: 400px; /* Or your preferred size */
  width: 100%;
}
</style>
