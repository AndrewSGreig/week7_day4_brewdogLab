<template lang="html">
  <div id="beerList">
    <p> In Beer List </p>
    <!-- {{beers}} -->
    <ul>
      <li v-for="(beer, index) in beers"  :key="index" >
        {{beer.name}}
<div id="right">
        <img :src="beer.image_url" :alt="beer.name">
</div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'beer-list',
    props: ['beers']

  }
</script>

<style lang="css" scoped>
#right img {
  width: 5%;
}
</style>
