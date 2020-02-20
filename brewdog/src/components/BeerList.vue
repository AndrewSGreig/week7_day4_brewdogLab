<template lang="html">
  <div id="beerList">
    <ul>
      <beer-item  v-for="(beer, index) in beers" :beer="beer" :key="index"></beer-item>

    </ul>

  </div>
</template>

<script>
import { eventBus } from '../main.js'
import BeerItem from './BeerItem.vue'
export default {
  name: 'beer-list',
  props: ['beers'],
  components: {
    "beer-item": BeerItem
  }
  }

</script>

<style lang="css" scoped>

</style>
