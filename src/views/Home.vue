<template>
  <!-- {{ dateBuilder(dataDate) }}
  new deaths: {{ stats.newDeaths }} -->
  <main v-if="!loading">
    <DataTitle :title="title" :date="dataDate" />
  </main>
  <main v-else class="flex flex-col align-center justify-center text-center">
    <div class="text-gray-500 text-3xl mt-10 mb-6">
      fetching Data
      <img :src="loadingImage" class="w-24 m-auto" alt="" />
    </div>
  </main>
</template>

<script>
// @ is an alias to /src
// import Header from '@/components/Header.vue';
import DataTitle from '../components/DataTitle.vue';

export default {
  name: 'Home',
  components: {
    DataTitle,
  },
  data() {
    return {
      loading: true,
      title: 'Global',
      dataDate: '',
      stats: {},
      countries: [],
      loadingImage: require('../assets/hourglass.gif'),
    };
  },
  methods: {
    async fetchData() {
      const res = await fetch('https://api.covid19api.com/summary');
      const data = await res.json();
      // console.log(data);
      return data;
    },
  },
  async created() {
    const data = await this.fetchData();
    console.log(data);
    this.dataDate = data.Date;
    this.stats = data.Global;
    this.countries = data.Countries;
    this.loading = false;
  },
};
</script>
