<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ title }}</h2>

    <div class="text-1xl mt-4 mb-10">
      <!-- <p>{{ dateBuilder(date) }}</p> -->
      Last updated: {{ timestamp }}
    </div>
  </div>
</template>

<script>
import moment from 'moment';

export default {
  name: 'DataTitle',
  props: {
    title: String,
    date: String,
  },
  methods: {
    dateBuilder(date) {
      let newDate = new Date(date).toDateString();
      return newDate;
    },
  },
  computed: {
    timestamp: function () {
      return moment(this.date).format('MMMM Do YYYY, h:mm:ss a');
    },
  },
};
</script>
