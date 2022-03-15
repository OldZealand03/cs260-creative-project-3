<template>
  <div id="app">
    <nav>
      <!-- <router-link to="/">Home</router-link> | -->
      <router-link to="/browse">Browse</router-link> |
      <router-link to="/saved">Sources</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    <router-view/>
    <div class='footer'>
      <div class='footer-item'>
        <a target='_blank' href='https://github.com/OldZealand03/cs260-creative-project-3'>
          <!-- <img height='50px' width='50px' src="GitHub-Mark-120px-plus.png"> -->
          Github
        </a>
        <br>
        Isaac Smith,
        <br>
        Vivian Solgere
      </div>
    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #6242b9;
}

.footer {
  position: fixed;
  bottom: 0%;
  width: 100%;
  height: 50px;
  text-align: left;
  align-items: left;
  font-size: 15px;
  color: #000;
  display: flex;
  justify-content: left;
  margin-bottom: 30px;
}
.footer-item {
  padding-right: 50px;
  padding-left: 50px;
}
</style>
