<template lang="html">
  <div id="beerList">
    <p> In Beer List </p>
    {{beers}}
    <ul>
      <li v-for="(beer, index) in beers"  :key="index" ></li>
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
</style>
