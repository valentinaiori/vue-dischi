<template>
  <div id="app">
    <HeaderComponent/>
    <MainComponent :albums ="albums"/>
    
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
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      albums: []
    }
  },

  created(){
    this.getAlbumData();
  },

  methods: {
    getAlbumData(){
      axios.get(this.apiUrl).then((response)=>{
      console.log(response);
      if(this.isResponseOK(response)){
        this.albums = response.data.response
      }
    })
  },
  
  isResponseOK({status}){
    return status === 200
  },
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
