<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h3>Our Cars</h3>
    <div class="cards">
      <div class="card" v-for="car in cars" :key="car.id">
        <!-- <router-link class-active="active" :to="`/car/${car.id}`">     alternative to line 8-->
        <router-link class-active="active" :to="{name: 'CarView', params:{id: car.id}}">
          <h4>{{car.make}}</h4>
          <h4>${{car.price}}</h4>
        </router-link>

        <!-- A programmatic routing/navigating can also be used with the use od div tag instead of the router-link tag(this makes it blue in color,underlined, since it is in form of an anchor tag) but if you want to use the above method and want to style the router-link, in your css,use anchor tag(a) to select the router-link tag for styling -->
      </div>
    </div>
  </div>
  
</template>

<script>
import carsData from "../data.json"
import {ref} from 'vue'
export default {
  // name: 'HomeView',
  setup(){
    const cars = ref(carsData)

    return{
      cars
    }
  }
}
</script>

<style scoped>
.active{
  text-decoration: none;
  color: red
}
.cards {
  display: flex;
  width: 1000px;
  flex-wrap: wrap;
  margin-top: 50px;
  justify-content: center;
}
.card {
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.207);
  padding: 15px;
  width: 150px;
  margin-right: 15px;
  cursor: pointer;
  margin-bottom: 20px;
}
.links {
  padding: 20px
}
.links a {
  margin: 0 5px
}

a{
  color:black;
  text-decoration: none;
}

</style>

