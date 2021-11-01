<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- box 1: cases -->
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Confirmed Cases</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">New Cases: </span>
        {{ formatNumber(stats.NewConfirmed) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total Cases:</span>
        {{ formatNumber(stats.TotalConfirmed) }}
      </div>
    </div>
    <!-- box 2: deaths -->
    <div class="shadow-md bg-red-100 p-10 text-center rounded">
      <h3 class="text-3xl text-red-900 font-bold mb-4">Deaths</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">New Deaths: </span>
        {{ formatNumber(stats.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total Deaths:</span>
        {{ formatNumber(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DataBoxes',
  props: {
    stats: Object,
  },
  methods: {
    // to add commas into numbers over 1000
    formatNumber(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    },
  },
};
</script>
