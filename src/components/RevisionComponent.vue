<template>
  <div class="bg-gray-100 rounded-lg p-4">
    <div class="flex items-center">
      <img src="@/assets/revision-logo.svg" alt="Revision Logo" class="h-8 w-8 mr-2 mb-7">
      <h3 class="text-lg font-bold mb-7">Revize v Budově</h3> 
    </div>
    <table class="w-full text-left table-auto border border-gray-200 rounded-lg ">
      <thead class="bg-gray-50">
        <tr>
          <th class="px-4 py-2 rounded-tl-lg">ID</th>
          <th class="px-4 py-2">NÁZEV SPRÁVY</th>
          <th class="px-4 py-2 rounded-tr-lg">STATUS</th>
          <th class="px-4 py-2 rounded-tr-lg"></th> 
        </tr>
      </thead>
      <tbody class="border-t border-gray-200"> 
        <tr v-for="(revision, index) in revisions" :key="revision.id" :class="index % 2 === 0 ? 'bg-white' : 'bg-gray-50'">
          <td class="px-4 py-2">{{ revision.id }}</td>
          <td class="px-4 py-2">{{ revision.name }}</td>
          <td class="px-4 py-2">
            <span v-if="revision.status === 'Prošlá'" class="bg-red-200 text-red-700 font-medium px-2 py-1 rounded-full">Prošlá</span>
            <span v-else-if="revision.status === 'Blížící se'" class="bg-yellow-200 text-yellow-700 font-medium px-2 py-1 rounded-full">Blížící se</span>
          </td>
          <td class="px-4 py-2 text-right">
            <a :href="revision.documentLink" target="_blank" class="text-blue-500 hover:text-blue-700">Detail</a>
          </td>
        </tr>
      </tbody>
    </table> 
    <div class="mt-4 flex justify-end space-x-2"> 
        <button class="bg-white text-black px-4 py-2 rounded-lg shadow">Všechny revize objektu</button> 
        <button class="bg-blue-500 text-white px-4 py-2 rounded-lg shadow flex items-center">
              <svg class="h-6 w-6 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                 <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v12m6-6H6" />
               </svg>
            Přidat nový
          </button>
</div>
  </div>
</template>

<script>
export default {
  props: ['revisions']
};
</script>