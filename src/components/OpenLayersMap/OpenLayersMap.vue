<script>
import 'ol/ol.css'
import Map from 'ol/Map'
import View from 'ol/View'
import TileLayer from 'ol/layer/Tile'
import OSM from 'ol/source/OSM'
import { useGeographic } from 'ol/proj'

export default {
  name: 'OpenLayersMap',
  props: {
    center: {
      type: Array,
      required: true
    },
    zoom: {
      type: Number,
      default: 10
    }
  },
  mounted() {
    useGeographic()
    new Map({
      target: this.$refs.map,
      layers: [
        new TileLayer({
          source: new OSM()
        })
      ],
      view: new View({
        center: this.center,
        zoom: this.zoom
      })
    })
  }
}
</script>

<template>
  <div ref="map" class="map"></div>
</template>

<style scoped>
.map {
  width: 100%;
  height: 100%;
}
</style>
