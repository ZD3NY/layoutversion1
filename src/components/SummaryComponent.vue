<template>
    <div class="bg-gray-100 rounded-lg p-4 sm:text-sm md:text-xs">
      <div class="flex items-center justify-start mb-7">
        <img src="@/assets/notes-logo.svg" alt="Notes Logo" class="h-6 w-6 mr-2 ms:h-8 sm:w-8 md:h-6 md:w-6">
        <h3 class="text-lg font-bold mb-2">Celkový souhrn</h3>
      </div>
      <div class="flex space-x-4 mb-4">
        <div v-for="(summary, index) in filteredSummaries" :key="index" class="flex items-center space-x-4">
          <img v-if="index === 0" :src="stairsIcon" alt="Stairs icon" class="h-6 w-6 sm:h-8 sm:w-8 md:h-6 md:w-6" />
          <img v-else-if="index === 1" :src="doorIcon" alt="Door icon" class="h-6 w-6 sm:h-8 sm:w-8 md:h-6 md:w-6" />
          <div class="ml-2">
            <p class="text-gray-700 font-medium text-xs sm:text-sm md:text-xs lg:text-lg">{{ summary.title }}</p>
            <p class="text-gray-500 text-xs md:text-xs lg:text-lg">{{ summary.value }}</p>
          </div>
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold rounded text-xs sm:py-2 sm:px-4 sm:text-sm md:py-1 md:px-2 md:text-xs lg:py-2 lg:px-4 lg:text-sm w-auto min-w-0" @click="summary.action">
            {{ summary.buttonText }}
          </button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import StairsIcon from '@/assets/stairs.svg';
  import DoorIcon from '@/assets/door.svg';
  
  export default {
    name: 'SummaryComponent',
    props: ['filteredSummaries'],
    data() {
      return {
        stairsIcon: StairsIcon,
        doorIcon: DoorIcon,
      };
    },
  }
  </script>
 
