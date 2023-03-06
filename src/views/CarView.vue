<template>
  <div v-if = "cars">
   <h2>CARS</h2>
    <p>{{car.make}}</p>
    <p>{{car.body}}</p>
    <p>{{car.price}}</p>
    <p>{{car.year}}</p>
  </div>
  <div v-else>
    <!-- The else here helps whenever a car route typed does not exist, i.e, http://localhost:8080/car/888dfd89, whereas from the data, where we have the params to be 1-10 due to the data id. a bit similar to 404 page, but this particular to CarView component(/car/:id) -->
    <h1>Car Not Found</h1>
  </div>

</template>

<script>
import {useRoute} from "vue-router"
import {ref, onBeforeMount} from "vue"
import cars from "../data.json"

export default {
	// name: "CarView",
  // data(){
  //   return{
  //     car: null,
  //     // id:this.$route.params.id,
  //     carsData: null
  //   }
  // },

  setup(){

    const car = ref(null)
    const route = useRoute()
    const {id} = route.params
    
    onBeforeMount(() =>{
      // const display = show.params
      car.value = cars.find((c) => c.id === parseInt(id) )
      console.log(id)
    })

    return{
      car,
      route,
      id,
      onBeforeMount
    }
  }

}
</script>

<style>

</style>