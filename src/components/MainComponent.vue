<template>
  <main>
    <SearchGenreComponent :options="genres" @selectedGenre="filterByGenre"/>
    <AlbumContainerComponent :albums="albumToDisplay"/>
  </main>
</template>

<script>
import axios from 'axios';
import SearchGenreComponent from './SearchGenreComponent.vue';
import AlbumContainerComponent from './AlbumContainerComponent.vue';



export default {
    name: 'MainComponent',
    components: {
        SearchGenreComponent,
        AlbumContainerComponent
    },

    data(){
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            albums: [],
            selectedGenre: '',
       }
    },

    created(){
        this.getAlbumData();
    },

    methods: {
        getAlbumData(){
            axios.get(this.apiUrl).then((response)=>{
                if(this.isResponseOK(response)){
                    console.log(response.data)
                this.albums = response.data.response
                }
            })
        },
  
        isResponseOK({status}){
            return status === 200
        },

        filterByGenre(genre){
            this.selectedGenre = genre;
            console.log(this.selectedGenre)
        },
    }, 

    computed:{
        genres(){
            const array= [];
            this.albums.forEach(album =>{
                if(!array.includes(album.genre)){
                    array.push(album.genre)
                }
            })
            console.log({genres: array})
            return array;
        },
        
        albumToDisplay(){
            console.log('ciao')
            const array = [];
            this.albums.forEach(album =>{
                if(this.selectedGenre.length === 0 || this.selectedGenre === album.genre){
                    array.push(album);
                }
            })
            return array;
        }

    },
}
</script>

<style lang="scss" scoped>
    main{
        background-color: #1e2d3b;
        color: white;
    }
</style>