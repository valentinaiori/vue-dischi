<template>
  <div id="app">
    <HeaderComponent/>
    <MainComponent :disks ="disks"/>
    
  </div>
</template>

<script>
import axios from 'axios';
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";

export default {
  name: 'App',
  data(){
    return {
      disks: [],
    }
  },

  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then(({status, data}) =>{
      if(status === 200){
        this.disks = data;
      }
    })
  },

  components: {
    HeaderComponent,
    MainComponent
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
