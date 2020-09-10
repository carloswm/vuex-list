<template>
  <div id="app" class="container">
    <Cabecera />
    <List />
  </div>
</template>

<script>
import Cabecera from './components/Cabecera.vue'
import List from './components/List'

export default {
  name: 'App',
  components: {
    Cabecera,
    List 
  }
}
</script>

<style>

</style>
