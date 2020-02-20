<template lang="html">
  <div id="fave-beers" v-if="beer">

    <p><span>Beer Name</span>: {{beer.name}}</p>
    <p>-----------------------------------</p>
  </div>
</template>

<script>
import BeerItem from './BeerItem.vue'

export default {
  name: "fave-beers",
  data: {
    faveBeers: []


  },
  components: {
    "fave-beer": FaveBeers
  },
  methods:{
    addToFavourites: function(){
      this.faveBeers.push(this.selectedBeer.name);
    }
  }
  </script>

  <style lang="css" scoped>
  </style>
