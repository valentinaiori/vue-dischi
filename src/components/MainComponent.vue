<template>
  <main>
    <div class="card-container">
        <div class="card" v-for="disk in disks" :key="disk.title">
            <p>{{disk.title}}</p>
        </div>
    </div>

  </main>
</template>

<script>

export default {
    name: 'MainComponent',

    props: {
        disks: Array,
    }
}
</script>

<style lang="scss" scoped>
    main{
        background-color: #1e2d3b;
        height: 700px;
    }

    p{
        color: white;
    }

</style>