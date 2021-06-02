<template>
  <div id="nav">
    <Header />
    <CatalogueSearchNav />
    <Products />
  </div>
  <router-view/>
</template>

<script>

import Header from './components/Header.vue';
import Products from './components/Products.vue';
import CatalogueSearchNav from './components/CatalogueSearchNav.vue';

export default {
  name: 'App',
  components:{
    Header,
    Products,
    CatalogueSearchNav
  }
}
</script>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;

    box-sizing: border-box;
  }
  body{
    color: #3F414E;
    font-family: 'Open Sans', sans-serif;
  }
  ul{
    list-style: none;
  }
  button,input{
    font-family: inherit;
    outline: none;
  }
  .wrapper{
    max-width: 1200px;
    width: 90%;
    margin: 0 auto;
  }
</style>
