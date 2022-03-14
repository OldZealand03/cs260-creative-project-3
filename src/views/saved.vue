<template>
<div>
    <SavedArticles />
</div>
</template>

<script>

import SavedArticles from '../components/SavedArticles.vue'

export default {
  name: 'Saved-articles',
  components: {
    SavedArticles
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