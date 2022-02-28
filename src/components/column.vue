<template>
    <div class="column" v-bind:name=name v-bind:squares=squares>
        <ul class="square-list">
            <li v-for="square in dataSquares" :key="square">
                <square :name="name + square.name" :color="square.color"/>
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
            dataSquares: this.squares,
            color: 0,
        }
    },
    methods: {
    },
    beforeMount() {
        // Set the starting color of each column component
        if(["a", "c", "e", "g"].indexOf(this.dataName) > -1) {
            this.color = 1;
        } else {
            this.color = 0 ;
        }

        // alternate the color for each square in the column
        for(let i = 0; i < this.dataSquares.length; i++) {
            // creating new property in the object in the dataSquares array
            // this object is passed in as a prop into the square component
            this.dataSquares[i].color = this.color;
            this.color = this.color === 0 ? 1 : 0;
        }
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