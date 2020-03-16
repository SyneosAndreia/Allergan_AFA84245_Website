<template>
    <div class="presentation-wrapp">
        <h1 class="bold-text">Master templates</h1>
        <div class="title-wrap">
            <div class="tittle-width">Cover</div>
            <div class="tittle-width">Event Name</div>
            <div class="tittle-width">Date added</div>
            <div class="tittle-width">Total size</div>
            <div class="tittle-width">Specs</div>
        </div>
    </div>
</template>


<script>
export default {
    name:'MainPage',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h1 {
        font-size: 36;
        text-align: left;

    }
    .bold-text {
        font-weight: bold;
    }

    .presentation-wrapp {
        width: 82%;
    }

    .title-wrap {
        width: 100%;
        display: flex;
        justify-content: flex-start;
        border-bottom: 1px solid #D1D1D1;
    }
</style>