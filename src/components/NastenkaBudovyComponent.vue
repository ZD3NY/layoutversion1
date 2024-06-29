<template>
  <div :class="{'pointer-events-none': showDialog}">
  <div class="flex justify-between items-center">
    <div>
      <h3 class="text-lg font-bold">Nastenka budovy</h3>
      <p class="text-gray-500">Details and application.</p>
    </div>
    <div class="flex items-center">
      <div class="flex items-center cursor-pointer pr-4" @click="showDialog = true">
          <img src="@/assets/trash-logo.svg" alt="Smazat budovu" class="h-6 w-6 text-red-500">
          <span class="text-red-500 ml-2">Smazat budovu</span>
      </div>
      <button class="flex items-center bg-white text-black px-2 py-1 rounded border border-black mr-4" @click="exportBuilding">
          <img src="@/assets/exp-icon.svg" alt="Exportovat" class="h-6 w-6">
          <span class="ml-2">Exportovat</span>
      </button>
    </div>
  </div>
  </div>
  <div v-if="showDialog" class="fixed inset-0 flex justify-center items-center z-50">
    <div class="fixed inset-0 bg-black bg-opacity-50"></div> 
    <div class="bg-white p-8 rounded-lg shadow-xl z-10 relative" style="pointer-events: all;">
      <p>Are you sure you want to delete this building?</p>
      <div class="flex justify-end space-x-4">
        <button @click="showDialog = false" class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          Close
        </button>
        <button class="mt-4 bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded">
          Delete
        </button>
      </div>
    </div>
  </div>
</template>

  
  <script>
  export default {
    name: 'NastenkaBudovyComponent',
    data() {
      return {
        showDialog: false,
      };
    },
  }
  </script>