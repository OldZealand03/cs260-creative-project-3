<template>
  <div class="wrapper">
    <div class="articles">
      <div class="title">
        <h2>Results</h2>
      </div>
      <div class="article" v-for="item in articles" :key="item">
        <h3>{{ item.title}}</h3>
        <p>{{ item.author}}</p>
        <p>{{ item.source.name}}</p>
        <p>{{  item.publishedAt  }}</p>
        <!-- Find a way to parse this date above ^^ -->
        <button class= "auto" @click="addToSaved(item)">Save Article</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ArticleList",
  props: {articles:Array},
  data() {
    return {
      obj: this.propsdata
    }
  },
  methods: {
    addToSaved(item){
      this.$root.$data.saved.push(item)
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

.articles {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.article {
  margin: 10px;
  margin-top: 50px;
  width: 600px;
}

/* .product img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #f2921d;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}

.price {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
} */
</style>
