<template lang="html">
  <div id="beer-details" v-if="beer">

    <p><span>Beer Name</span>: {{beer.name}}</p>
    <p><span>Tagline</span>: {{beer.tagline}}</p>
    <div id="beerImg">
      <img :src="beer.image_url" :alt="beer.name">
    </div>
    <!-- <div v-if="!favouriteBeers.includes(selectedBeer.name)">
      <input type='submit' value='Add to Favourites' v-on:click="addToFavourites" />
    </div> -->
    <p>---------------------------------------------------</p>
  </div>
</template>

<script>
export default {
  name: 'beer-details',
  props: ['beer']
}
</script>

<style lang="css" scoped>
#beerImg img {
  width: 20%;
}
</style>
