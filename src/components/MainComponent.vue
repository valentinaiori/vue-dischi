<template>
  <main>
    <SelectAreaComponent/>
    <div class="card-container">
        <div class="card" v-for="album in albums" :key="album.title">
            <div>
                <img :src="album.poster">
            </div>
            <p class="album-title">{{album.title}}</p>
            <p class="author">{{album.author}}</p>
            <p class="year">{{album.year}}</p>
        </div>
    </div>

  </main>
</template>

<script>
    import SelectAreaComponent from './SelectAreaComponent.vue'

export default {
    name: 'MainComponent',
    props: {
       albums: Array,
    }, 
    components: {
        SelectAreaComponent
    }
}
</script>

<style lang="scss" scoped>
    main{
        background-color: #1e2d3b;
        color: white;
    }

    .card-container{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: stretch;
        flex-wrap: wrap;
        width: 1000px;
        text-align: center;
        height: 100%;
        padding-top: 30px;
        padding-bottom: 30px;
        
        
    
        img{
            width: 130px;
            height: 140px;
            padding-top: 20px;
        }

        .card{

            display: flex;
            flex-direction: column;
            width: calc(100% / 5);
            flex-wrap: wrap;
            width: 150px;   
            flex-wrap: wrap;   
            background-color: #2e3a46;
            margin: 10px;
        }

        .album-title{
            padding-top: 20px;
            padding-bottom: 20px;
        }

        .author, .year{
            color: grey;
        }

        .year{
            font-size: 0.8rem;
            padding-bottom: 10px;
        }
    
    }


</style>