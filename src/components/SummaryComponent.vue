<template>
    <div class="bg-gray-100 rounded-lg p-4">
      <div class="flex items-center justify-start mb-7">
        <img src="@/assets/notes-logo.svg" alt="Notes Logo" class="h-8 w-8 mr-2">
        <h3 class="text-lg font-bold mb-2">Celkový souhrn</h3>
      </div>
      <div class="flex space-x-4 mb-4">
        <div v-for="(summary, index) in filteredSummaries" :key="index" class="flex items-center space-x-4">
          <img v-if="index === 0" :src="stairsIcon" alt="Stairs icon" class="h-8 w-8" />
          <img v-else-if="index === 1" :src="doorIcon" alt="Door icon" class="h-8 w-8" />
          <div class="ml-2">
            <p class="text-gray-700 font-medium">{{ summary.title }}</p>
            <p class="text-gray-500">{{ summary.value }}</p>
          </div>
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="summary.action">
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
 