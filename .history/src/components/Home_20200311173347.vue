<template>
    <div class="title-wrap">
        <div class="tittle-width">Cover</div>
        <div class="tittle-width">Event Name</div>
        <div class="tittle-width">Date added</div>
        <div class="tittle-width">Total size</div>
        <div class="tittle-width">Specs</div>
    </div>
</template>


<script>
export default {
    name:'MainPage',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .title-wrap {
        width: 100%;
        display: flex;
        justify-content: flex-start;
    }
</style>