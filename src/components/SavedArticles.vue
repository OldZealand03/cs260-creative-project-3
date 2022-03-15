<template>
    <div class="wrapper">
      <div class="articles">
        <div class="title">
          <h2>Your Saved Articles</h2>
        </div>
        <div class="article" v-for="article in this.$root.$data.saved" :key="article.id">
          <div class="info">
            <h3>{{ item.title}}</h3>
            <p>{{ item.author}}</p>
            <p>{{ item.source.name}}</p>
          </div>
          <button @click="deleteFromCart(article)" class="auto">Delete</button>
        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: "SavedArticles",
  props: {articles:Array},
  methods: {
    deleteFromCart(article) {
      const index = this.$root.$data.saved.indexOf(article);
      if (index > -1) {
        this.$root.$data.saved.splice(index, 1);
      }
    },
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
