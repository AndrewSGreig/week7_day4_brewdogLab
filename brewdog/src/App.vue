<template>
  <div id="app">
    <h1>Brewdog Beers </h1>
    <beer-list :beers="beers"></beer-list>
    <beer-details :beers="selectedBeer"></beer-details>

    <!-- <h2>Favourite Beers</h2>
    <ul v-for="beer in faveBeers">
      <li>{{beer}}</li>
    </ul> -->
  </div>
</template>

<script>
import BeerList from './components/BeerList.vue'
import { eventBus } from './main.js'
import BeerDetails from './components/BeerDetails.vue'
// import FaveBeers from './components/FaveBeers.vue'

export default {
  name: 'App',
  data(){
    return {
      beers: [],
      selectedBeer: null
    }
  },
  components: {
    "beer-list": BeerList,
    "beer-details": BeerDetails,
    // "fave-beer": FaveBeers

  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer

    })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color:ee #2c3e50;
  margin-top: 60px;
}
</style>
