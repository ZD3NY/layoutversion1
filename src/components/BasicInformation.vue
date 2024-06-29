<template>
  <div class="bg-gray-100 rounded-lg p-4">
    <div class="flex items-center justify-between mr-2 mb-7">
      <div class="flex items-center">
        <img src="@/assets/info-icon.svg" alt="Info Icon" class="h-6 w-6 mr-2">
        <h3 class="text-lg font-bold">Základní informace</h3>
      </div>
      <a href="#" class="flex items-center text-blue-500 hover:text-blue-700 transition-colors">
        <img src="@/assets/pen-icon.svg" alt="Edit Icon" class="h-4 w-4 mr-1"> 
        Upravit údaje
      </a>
    </div>
    <div class="grid grid-cols-4 gap-4">
      <div v-for="(item, index) in firstHalf" :key="`first-${index}`" class="col-span-2">
        <div class="flex justify-between relative pb-2">
          <span class="text-gray-500">{{ item.label }}</span>
          <span class="text-black">{{ item.value }}</span>
          <div class="absolute bottom-0 left-0 right-0 border-b border-gray-300"></div>
        </div>
      </div>
      <div v-for="(item, index) in secondHalf" :key="`second-${index}`" class="col-span-2">
        <div class="flex justify-between relative pb-2">
          <span class="text-gray-500">{{ item.label }}</span>
          <span class="text-black">{{ item.value }}</span>
          <div class="absolute bottom-0 left-0 right-0 border-b border-gray-300"></div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      basicInformation: [
        { label: 'Označení', value: 'Projekt A123' },
        { label: 'Vlastník', value: 'Jan Novák' },
        { label: 'Správce', value: 'Eva Dvořáková' },
        { label: 'Využití', value: 'Kancelářské prostory' },
        { label: 'Typ', value: 'Komerční budova' },
        { label: 'Město', value: 'Praha' },
        { label: 'Ulice', value: 'Václavské náměstí' },
        { label: 'Číslo popisné', value: '846/1' },
        { label: 'PSČ', value: '110 00' },
        { label: 'Katastr', value: 'Praha 1' }
      ]
    };
  },
  computed: {
    firstHalf() {
      return this.basicInformation.slice(0, 5);
    },
    secondHalf() {
      return this.basicInformation.slice(5);
    }
  }
};
</script>