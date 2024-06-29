<template>
  <div>
    <div class="flex items-center">
      <img src="@/assets/map-icon.svg" alt="Map Icon" class="h-8 w-8 mr-2 mb-7">
      <h3 class="text-lg font-bold mb-7">Mapy</h3>
    </div>
    <div class="maps-container flex flex-col md:flex-row">
      <div class="map-container w-full md:w-1/2">
        <div class="square-aspect-ratio">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1284.0835708639997!2d17.90010402738622!3d49.93320498497198!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x4713d86ab4e8016d%3A0x72bd6fd071bfafed!2zSHJhZGVja8OhIDY2NS8xNywgNzQ2IDAxIE9wYXZhIDEtUMWZZWRtxJtzdMOt!5e0!3m2!1sen!2scz!4v1719586980305!5m2!1sen!2scz" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
      </div>
      <div class="map-container w-full md:w-1/2">
        <div class="square-aspect-ratio">
          <iframe src="https://www.google.com/maps/embed?pb=!4v1719588058616!6m8!1m7!1sUOnWTM3slDPPfWVmFmZzaQ!2m2!1d49.93377347257546!2d17.90120509924106!3f152.51854067670502!4f-0.1892271140772408!5f0.7820865974627469" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MapComponent',
}
</script>

<style>
/* Ensure the maps-container takes the full width */
.maps-container {
  width: 100%;
}
/* Adjust the map-container margin as needed */
.map-container {
  margin-bottom: 2rem; /* Add space between stacked maps on smaller screens */
}
/* Define or adjust the square-aspect-ratio class to maintain aspect ratio */
.square-aspect-ratio {
  position: relative;
  width: 100%;
  padding-top: 56.25%; /* 16:9 Aspect Ratio */
}
.square-aspect-ratio iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>