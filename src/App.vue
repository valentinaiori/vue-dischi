<template>
  <div id="app">
    <HeaderComponent/>
    <MainComponent/>
    
  </div>
</template>

<script>

import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";

export default {
  name: 'App',
  
  components: {
    HeaderComponent,
    MainComponent,
  }

}

</script>

<style lang="scss">

  *{
  margin: 0 auto;
  padding: 0;
  box-sizing: border-box;
 }

 #app {
  font-family: Arial, Helvetica, sans-serif;
}

</style>
