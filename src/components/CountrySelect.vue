<template>
  <br />
  <select
    class="mt-10 form-select block w-full border p-3 rounded"
    name="countries"
    id=""
    v-model="selected"
    @change="onChange"
  >
    <option value="0">Select a country</option>
    <option :value="country.ID" v-for="country in countries" :key="country.ID">
      {{ country.Country }}
    </option>
  </select>
</template>

<script>
export default {
  name: 'CountrySelect',
  props: {
    countries: Array,
  },
  data() {
    return {
      selected: 0,
    };
  },
  methods: {
    onChange() {
      const selectedCountry = this.countries.find(
        (item) => item.ID === this.selected
      );
      this.$emit('get-country', selectedCountry);
    },
  },
};
</script>
