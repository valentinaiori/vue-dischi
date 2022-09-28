<template>
    <div class="select">
        <select v-model="userSelection" @change="changeGenres">
            <option value="">Nessuno selezionato</option>
            <option v-for="option in options" :key="option" :value="option">
                {{ option }}
            </option>
        </select>
    </div>
  
</template>

<script>
export default {
    name: 'SearchGenreComponent', 
    data(){
        return {
            userSelection: '',
        }
    },
    props: {
        options: Array,
    },
    methods: {
        changeGenres(){
            console.log(this.userSelection);
            this.$emit('selectedGenre', this.userSelection);
        }
    }
}
</script>

<style lang="scss" scoped>
    select{
        width: 180px;
        background-color: hsl(210deg, 22%, 23%);
        color: white;
        padding: 10px;
        margin: 20px 20px;
    }

</style>