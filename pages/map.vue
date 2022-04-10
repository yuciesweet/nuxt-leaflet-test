<template>
    <div id="map">
     <no-ssr>
       <!-- 気仙沼大島の緯度・経度 -->
       <l-map :zoom="zoom" :center="center">
         <l-tile-layer :url="url"></l-tile-layer>
         <l-marker v-for="marker of marker" :lat-lng="marker"}></l-marker>
       </l-map>
     </no-ssr>
    </div>
  </template>

<script type="module" lang="ts">
import Vue from "../node_modules/vue/dist/vue.esm"   

export default{
      data() {
        return{
          // leafletの設定
          center: [38.856355,140.615593],
          zoom: 12,
          url: "https://{s}.tile.osm.org/{z}/{x}/{y}.png",
          // マーカーを置く場所一覧（観光地）
          marker: {
            center:  [38.856355,140.615593],
            kugunaribeach: [38.873171,140.63164],
            mtkame: [38.87373,140.617855],
            tatsumai: [38.830445,140.624526],
            kodanobeach: [38.851971,140.622216],
            bridge: [38.878459,140.606309]
          }
        }
      }
    }
</script>

<style scoped>
    #map {
        height: 400px;
        width: 400px;
    }
</style>