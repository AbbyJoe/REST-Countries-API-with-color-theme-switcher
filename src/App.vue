<template>
  <div id="app">
    <Navbar/>
    <router-view/>
  </div>
</template>
<script>
import Navbar from './components/Navbar'
export default {
  components: {
    Navbar,
  }
}
</script>
<style>
  .container-fluid {
    width: 93%;
  }
 
</style>
