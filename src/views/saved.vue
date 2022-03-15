<template>
<div>
    <SavedArticles :articles="this.$root.$data.saved"/>
</div>
</template>

<script>

import SavedArticles from '../components/SavedArticles.vue'

export default {
  name: 'Saved-articles',
  components: {
    SavedArticles
  },
}
</script>