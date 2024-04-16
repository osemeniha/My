<template>
  <Header></Header>
  <Tracker></Tracker>
</template>

<script>
import Header from "./components/Header.vue";
import ToDo from "./components/ToDo.vue";
import Tracker from "./components/Tracker.vue"
export default {
  name: 'App',
  components: {
    Header,
    ToDo,
    Tracker
  }
}
</script>

<style>
#app {
  width: 100%;
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
