<template>
  <div class="browse">
    <h1>Browse</h1>
    <div class="wrapper">
      <div class="search">
        <form class="pure-form">
          <i class="fas fa-search"></i><input v-model="searchText" />
        </form>
      </div>
    <div class="button">
      <button @click="callAPI">GO!</button>
    </div>
    </div>
    <p>Why is the right side of the search box not colored? ^^^</p>
    <ArticleList :articles="list" />




  </div>
</template>

<script>
import ArticleList from "../components/ArticleList.vue";

// let testQuery = "tesla";
// callAPI(testQuery);

// var json_object;

export default {
  name: "BrowseStuff",
  components: {
    ArticleList,
  },
  data(){
    return {
      searchText: "tesla",
      list: []
    }
  },
  methods: {
    callAPI() {

      var today = new Date()
      let self = this;
      let userInput = this.searchText;
      console.log(userInput);

      let u1 = "https://newsapi.org/v2/everything?q=";
      let u2 = "&from=2022-02-";
      let day = String(today.getDate()+1);
      console.log(day);
      let u3 = "&sortBy=publishedAt&apiKey=27ba76b43e724c38a32517d7b92abba4";

      let url = u1 + userInput + u2 + day + u3;
      console.log(url)

      fetch(url)
        .then(function (response) {
          return response.json();
        })
        .then(function (json) {
          console.log(json.articles);
          console.log(json.articles[0].author);
          self.list = json.articles;
          // let articles = json;
          // Figure out a way to pass this json object as a property to the next BrowseStuff vue
        });

    },
  },
  //   props: {
  //     products: Array,
  //   },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
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
