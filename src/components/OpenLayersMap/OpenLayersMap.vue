<script>
import 'ol/ol.css'
import Map from 'ol/Map'
import View from 'ol/View'
import TileLayer from 'ol/layer/Tile'
import OSM from 'ol/source/OSM'
import Feature from 'ol/Feature'
import Point from 'ol/geom/Point'
import { fromLonLat } from 'ol/proj'
import { Vector as VectorLayer } from 'ol/layer'
import { Vector as VectorSource } from 'ol/source'

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
    },
    markers: {
      type: Array,
      default: () => []
    }
  },
  mounted() {
    const map = new Map({
      target: this.$refs.map,
      layers: [
        new TileLayer({
          source: new OSM()
        }),
        new VectorLayer({
          source: new VectorSource()
        })
      ],
      view: new View({
        center: fromLonLat(this.center),
        zoom: this.zoom
      })
    })

    const vectorSource = map.getLayers().item(1).getSource()
    this.markers.forEach((marker) => {
      const markerFeature = new Feature({
        geometry: new Point(fromLonLat(marker.lngLat))
      })
      vectorSource.addFeature(markerFeature)
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
