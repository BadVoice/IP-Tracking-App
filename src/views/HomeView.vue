
<template>
  <div class="flex flex-col h-screen max-h-screen">
<!-- Search / Results-->
    <div 
    class=" z-20 flex justify-center realtive bg-hero-pattern bg-cover px-4 pt-8 pb-32"
    
    >
<!-- Search / input-->
      <div class="w-full max-w-screen-sm">
        <h1 class="text-white text-center text-3xl pb-4 ">
          IP Address Tracker
        </h1>
        <div class="flex">
          <input 
            class="flex-1 py-3 px-2 rounded-tl-md rounded-bl-md focus:outline-none" type="text" 
            placeholder="Search for any IP address pr leave empty to get your ip info" />
            <i class="
            cursor-pointer bg-black text-white px-4 rounded-tr-md
            rounded-br-md 
            fas fa-solid fa-chevron-right 
            flex items-center "></i>
        </div>
      </div>
<!-- IP Info--> 
      <IPInfo />
    </div>

<!-- Map -->
    <div id="mapid" class="h-full z-10"></div>
  </div>
</template>


<script setup>
import IPInfo from '../components/IPInfo.vue';
import leaflet from 'leaflet'
import { onMounted } from '@vue/runtime-core';

let mymap;

  onMounted(() => {
    mymap = leaflet.map("mapid").setView([42.5145, -83.0147], 9);
      leaflet
        .tileLayer(
          "https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token=pk.eyJ1IjoiYmFkdm8xY2UiLCJhIjoiY2w2dXdneXd5MDRtbjNjcGZlamhndzFjZyJ9.xYf7TB6PpSezpB6AOyQSQQ",
          {
            attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>',
            maxZoom: 18,
            id: "mapbox/streets-v11",
            tileSize: 512,
            zoomOffset: -1,
            accessToken:
              "pk.eyJ1IjoiYmFkdm8xY2UiLCJhIjoiY2w2dXdneXd5MDRtbjNjcGZlamhndzFjZyJ9.xYf7TB6PpSezpB6AOyQSQQ",
          }
        )
        .addTo(mymap);
  
      })

        

</script>

