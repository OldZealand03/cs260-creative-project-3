<template>
  <div class="saved">
    <h1>Your Saved Articles</h1>
    <div class="wrapper">
    </div>
    //<ArticleList :articles="list" />
  //</div>
</template>

<script>
export default {
  name: "SavedArticles",
  props: {articles:Array},
  data() {
    return {
      savedList: []
    }
  },
  methods: {
 },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>
