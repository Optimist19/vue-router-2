<template>
  <router-link active-class="active" :to="{name:'Home'}">To Home|</router-link>
  <router-link active-class="active" :to="{name:'About'}">To About|</router-link>
  <!-- <router-link active-class="active" :to="{name:'CarView'}">To Car|</router-link> -->
  <router-view/>
</template>

<style scoped>
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

.active {
  color: green;
}
</style>
