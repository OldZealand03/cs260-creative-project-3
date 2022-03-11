<template>
<div>
    <BrowseStuff />
</div>
</template>

<script>

import BrowseStuff from '../components/BrowseStuff.vue'

export default {
  name: 'Browse-stuff',
  components: {
    BrowseStuff
  },
//   data() {
//     return {
//       country: '',
//     }
//   },
//   computed: {
//     products() {
//       return this.$root.$data.products.filter(product => product.country === this.country);
//     }
//   },
//   methods: {
//     select(country) {
//       this.country = country;
//     }
//   }
}
</script>