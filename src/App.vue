<template>
  <div id="app">
    <!-- <Catalogue />  -->
    <CatalogueAxios />
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {
    // Catalogue: () => import('./components/Catalogue')
    CatalogueAxios: () => import('./components/CatalogueAxios')
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif; 
  color: #2c3e50;
  margin-top: 60px;
}

img {
  display: block;
  margin: 0 auto
}

.container {
    width: 1200px;
    margin: 0 auto;  
}

.text-center {
  text-align: center;
}  
</style>
