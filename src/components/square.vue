<template>
    <div class="square" :style="{backgroundColor: backgroundColor, color: textColor}">{{ dataName }}</div>
</template>

<script>
export default {
    name: "square",
    props: {
        name: String,
        color: Number,
    },
    data() {
        return {
            dataName: this.name,
            dataColor: this.color,
            backgroundColor: this.color === 0 ? "#FFF" : "#000",
            textColor: this.color === 1 ? "#FFF" : "#000"
        }
    },
    created() {

    }
}
</script>

<style>
    .square {
        width: 75px;
        height: 75px;
        padding: 0px;
        margin: none;
        border: 1px solid black;
    }
</style>