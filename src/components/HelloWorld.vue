<script setup lang="ts">
import { ref, computed } from "vue";
import "leaflet/dist/leaflet.css";
import { LMap, LMarker, LIcon } from "@vue-leaflet/vue-leaflet";

let visible = ref(true);
const toggle = function () {
  visible.value = !visible.value;
};
</script>

<template>
  <l-map
    ref="map"
    :center="[0, 0]"
    :zoom="2"
    class="map"
    style="width: 400px; height: 400px"
  >
    <template v-if="visible">
      <l-marker :lat-lng="[0, 0]">
        <l-icon>#</l-icon>
      </l-marker>
    </template>
  </l-map>

  <br />
  <button @click="toggle">Toggle Marker</button>
</template>
