<template>
    <div class="select">
        <select name="select-area">
            <option value="All">All</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Pop">Pop</option>
            <option value="Rock">Rock</option>
        </select>
    </div>
  
</template>

<script>
export default {
    name: 'SelectAreaComponent'
}
</script>

<style lang="scss" scoped>
    select{
        width: 130px;
        background-color: hsl(210deg, 22%, 23%);
        color: white;
        padding: 10px;
        margin: 20px 20px;
    }

</style>