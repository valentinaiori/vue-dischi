<template>
  <header>
    <img src="../assets/img/logo.svg" alt="Spotify">
  </header>
</template>

<script>
export default {
    name: 'HeaderComponent'
}
</script>

<style lang="scss" scoped>
    header{
        background-color: #2e3a46;
        height: 80px;
    }

    img{
        height: 70px;
        width: 200px;
        padding: 10px;
    }

</style>