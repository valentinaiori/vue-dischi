<template>
  <main>
    <div class="card-container">
        <div class="card" v-for="album in albums" :key="album.title">
            <div>
                <img :src="album.poster">
            </div>
            <p>{{album.title}}</p>
        </div>
    </div>

  </main>
</template>

<script>

export default {
    name: 'MainComponent',
    props: {
       albums: Array,
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
        width: 800px;
        text-align: center;
        height: 100%;
        
    
        img{
            width: 100px;
            height: 100px;
        }

        .card{

            display: flex;
            flex-direction: column;
            width: calc(100% / 5);
            flex-wrap: wrap;
            background-color:#2e3a46;
            height: 300px;
            width: 200px;   
            padding: 10px;    
            flex-wrap: wrap;   
        }
    }


</style>