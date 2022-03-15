<template>
    <div class="wrapper">
      <div class="articles">
        <div class="title">
          <h2>Your Saved Articles</h2>
        </div>
        <div class="article" v-for="article in this.$root.$data.saved" :key="article.id">
          <div class="info">
            <h3>{{ article.title}}</h3>
            <p>{{ article.author}}     {{ article.source.name}}</p>
          </div>
          <button @click="deleteFromSaved(article)" class="auto">Delete</button>
        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: "SavedArticles",
  methods: {
    deleteFromSaved(article) {
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

.article {
  margin: 10px;
  margin-top: 50px;
  width: 1200px;
  display : inline-block;
  box-sizing: border-box;
  border : 1px solid black;
  margin : 5px 5px 5px 5px;
  padding : 5px 5px 5px 5px;
  text-align: left;

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

p {
  display: block,
}
</style>
