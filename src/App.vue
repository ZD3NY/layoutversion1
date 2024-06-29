<template>
  <div class="p-4">
    <div class="flex items-center justify-between mb-4">
      <div class="flex items-center">
        <router-link to="/">
          <img src="@/assets/home_icon.svg" alt="Home" class="h-6 w-6 mr-4" />
        </router-link>
        <span class="text-gray-500 text-sm">
          Evidence majetku > Nemovitý majetek > Správa budov > Budova Havířov
        </span>
      </div>
      <div class="flex items-center">
        <button><img src="@/assets/bell.svg" alt="Different Logo" class="h-6 w-6 mr-4" /></button>
        <button><img src="@/assets/photo.png" alt="Rounded" class="h-8 w-8 rounded-full" /></button>
      </div>
    </div>
    <header>
      <h1 class="text-3xl font-bold text-left mb-4">Budova Havířov 3</h1>
    </header>
    <div class="pb-6">
      <div class="border-b-2 border-gray-200 mx-[-1rem]"></div>
    </div>
    <div class="mb-7">
       <NastenkaBudovyComponent/>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div class="flex flex-col space-y-4">
        <div>
          <SummaryComponent :filteredSummaries="filteredSummaries" />
        </div>
        <div>
          <BasicInformation :bacicInformation="basicInformation"/>
        </div>
        <EnergyComponent :chartData="energyChartData"></EnergyComponent>
      </div>
      <div class="flex flex-col space-y-4">
        <div>
          <RevisionComponent :revisions="revisions" />
        </div>
        <div>
        <DocumentsComponent :revisions="revisions" />
      </div>
        <div>
        <DocumentsComponent :revisions="revisions" />
      </div>
      </div>
    </div>
    <div class="w-full pt-8 pb-8">
        <MapComponent />
      </div>
  </div>
</template>
<script>
import SummaryComponent from './components/SummaryComponent.vue'; 
import RevisionComponent from './components/RevisionComponent.vue'; 
import BasicInformation from './components/BasicInformation.vue';
import DocumentsComponent from './components/DocumentsComponent.vue';
import EnergyComponent from './components/EnergyComponent.vue';
import MapComponent from './components/MapComponent.vue';
import NastenkaBudovyComponent from './components/NastenkaBudovyComponent.vue';

export default {
  components: {
    SummaryComponent,
    RevisionComponent,
    BasicInformation,
    DocumentsComponent,
    EnergyComponent,
    MapComponent,
    NastenkaBudovyComponent,
  },
  name: 'App',
  data() {
    return {
      summaries: [
        { title: 'Počet podlaží', value: 3, buttonText: 'Přidat podlaží', action: () => this.addFloor() },
        { title: 'Počet místností', value: 16, buttonText: 'Přidat místnost', action: () => this.addRoom() }
      ],
      revisions: [
        { id: 1, name: 'Elektrická revize', status: 'Prošlá', documentLink: 'https://example.com/doc1' },
        { id: 2, name: 'Plynová revize', status: 'Blížící se',documentLink: 'https://example.com/doc1' },
        { id: 3, name: 'Servis 140 000 Kc', status: 'Blížící se', documentLink: 'https://example.com/doc1' },
        { id: 4, name: 'Servis', status: 'Blížící se', documentLink: 'https://example.com/doc1' },
        { id: 5, name: 'Servis 120 000 Kc', status: 'Prošlá', documentLink: 'https://example.com/doc1' },
        { id: 6, name: 'STK', status: 'Blížící se', documentLink: 'https://example.com/doc1' },
      ], 
    }
  },
  methods: {
    addFloor() {
      const floorSummary = this.summaries.find(summary => summary.title === 'Počet podlaží');
      if (floorSummary) {
        floorSummary.value += 1;
      }
    },
    addRoom() {
      const roomSummary = this.summaries.find(summary => summary.title === 'Počet místností');
      if (roomSummary) {
        roomSummary.value += 1;
      }
    }
  },
  computed: {
    filteredSummaries() {
      return this.summaries.filter(summary => summary.title === 'Počet místností' || summary.title === 'Počet podlaží');
    }
  }
};
</script>