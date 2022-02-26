<template>
    <div class="square" >{{ dataName }}</div>
</template>

<script>
export default {
    name: "square",
    props: {
        name: String,
    },
    data() {
        return {
            dataName: this.name
        }
    }
}
</script>

<style>
    .square {
        width: 50px;
        height: 50px;
        padding: 0px;
        margin: none;
        border: 1px solid black;
    }
</style>