<template>
  <div id="app">
    <router-link to="/">home</router-link>|
    <router-link to="/about">about</router-link>|
    <router-link to="/about2">about2</router-link>
    <router-view></router-view>
  </div>
</template>


<style>
.input-row {
  display: flex;
}

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
  color: #42b983;
}
</style>
