<template lang="html">
  <div id="beer-item">
    <div id="beerImg">
      <!-- <img :src="beer.image_url" :alt="beer.name"> -->

    <p v-on:click="handleClick">{{beer.name}}<img :src="beer.image_url" :alt="beer.name"></p>
</div>
    <beer-details v-if="clicked" :beer="beer"></beer-details>

  </div>
</template>

<script>
import BeerDetails from './BeerDetails.vue'
import { eventBus } from '../main.js';
export default {
  name: 'beer-item',
  props: ['beer'],
  data(){
    return{
      clicked: false
    }
  },
  components: {
    'beer-details': BeerDetails
  },
  methods: {
    handleClick(){
      // eventBus.$emit('beer-selected', this.beer)
      this.clicked = true
      
    }
  }
}
</script>


<style lang="css" scoped>
#beerImg img {
  width: 3%;
}
</style>
