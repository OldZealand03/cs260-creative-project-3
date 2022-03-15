<template>
  <div class="wrapper">
    <div class="articles">
      <div class="article" v-for="item in articles" :key="item">
      <div class="leftStuff">
          <h3>{{ item.title }}</h3>
          <p>{{ item.author }} | {{ item.source.name }}</p>
          <!-- Find a way to parse this date above ^^ -->
          <button class= "auto" @click="addToSaved(item)">Save Source</button>
      </div>
        <img :src="item.urlToImage"/>
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
      console.log(item)
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
  width: 1200px;
  display : inline-block;
  box-sizing: border-box;
  border : 1px solid black;
  margin-left: 10%;
  margin-right: 10%;
  margin-top: 10px;
  margin-bottom: 10px;
  padding : 5px 5px 5px 5px;
  text-align: left;
}

.leftStuff {
  float: left;
  width: 800px;
}

img {
  width: 180px;
  height: 140px;
  float: right;
  vertical-align: middle;
}

h3, p, button {
  margin-left: 20px;
  margin-bottom: 20px;
}
</style>
