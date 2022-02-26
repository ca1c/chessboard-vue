<template>
    <div class="column" v-bind:name=name v-bind:squares=squares>
        <ul class="square-list">
            <li v-for="square in dataSquares" :key="square">
                <square :name="name + square.name"/>
            </li>
        </ul>
    </div>
</template>

<script>
import square from './square.vue';

export default {
    name: "column",
    props: {
        squares: Array,
        name: String,
    },
    components: {
        square: square
    },
    data() {
        return {
            dataName: this.name,
            dataSquares: this.squares
        }
    },
    created() {
    }
}
</script>

<style>
    .square-list{ 
        list-style-type:none;
        float: left;
        padding: 0px;
    }
</style>