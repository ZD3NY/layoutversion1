<template>
    <div class="bg-gray-100 rounded-lg p-4">
      <div class="flex items-center">
        <img src="@/assets/energy-logo.svg" alt="Energy Logo" class="h-8 w-8 mr-2 mb-7">
        <h3 class="text-lg font-bold mb-7">Energetická náročnost</h3>
      </div>
      <div class="flex justify-center items-center">
        <BarChart />
      </div>
      <div class="grid grid-cols-1 gap-4">
        <div v-for="(item, index) in energyStats" :key="`item-${index}`" class="col-span-1">
          <div class="flex justify-between relative pb-2">
            <span class="text-gray-500">{{ item.label }}</span>
            <span class="text-black">{{ item.value }} <span v-html="item.unit"></span></span>
            <div class="absolute bottom-0 left-0 right-0 border-b border-gray-300"></div>
          </div>
        </div>
      </div>
      <div class="mt-4 flex justify-end space-x-2">
        <button class="bg-white text-black px-4 py-2 rounded-lg shadow" @click="showAllMeasurements">Všechny měření</button>
        <button class="bg-blue-500 text-white px-4 py-2 rounded-lg shadow flex items-center" @click="addNewMeasurement">
          <svg class="h-6 w-6 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v12m6-6H6" />
          </svg>
          Přidat nové měření
        </button>
      </div>
    </div>
</template>
  
  <script>
 import BarChart from '@/components/BarChart.vue'
 export default{
    data() {
    return {
      energyStats: [
        { label: 'Elektřina', value: 20, unit: 'mWh' },
        { label: 'Teplo', value: 79,unit: "mWh" },
        { label: 'Voda', value: 100, unit: 'm&sup3;' },
        { label: 'Plyn', value: 100, unit: 'm&sup3;' },
      ]
    };
  },
    components: {
        BarChart}

 }
  
 
  </script>