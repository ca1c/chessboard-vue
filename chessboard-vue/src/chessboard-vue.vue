<template>
  <div id="board">
    <ul class="columns">
      <li class="column" v-for="file in files" :key="file.name">
        <column :name="file.name" :squares="ranks"/>
      </li>
    </ul> 
  </div>
</template>

<script>
import column from './components/column.vue';

export default {
  name: "chessboard-vue", // vue component name
  components: {
    column: column
  },
  data() {
    return {
      files: [
        { name: "a"},
        { name: "b"},
        { name: "c"},
        { name: "d"},
        { name: "e"},
        { name: "f"},
        { name: "g"},
        { name: "h"},
      ],
      ranks: [
        { name: "8"},
        { name: "7"},
        { name: "6"},
        { name: "5"},
        { name: "4"},
        { name: "3"},
        { name: "2"},
        { name: "1"},
      ],
      board: [],
      color: "light",
    }
  },
  methods: {
    initBoard() {
      for(let i = 0; i < this.files.length; i++) {
        for(let j = 0; j < this.ranks.length; j++) {
          this.board.push({name: this.files[i] + this.ranks[j], color: this.color});
          this.color = this.color === "light" ? "dark" : "light";
        }
      }
    },
    loadBoard() {
      this.initBoard();
      // console.log(this.board); 
    }
  },
  created() {
    this.loadBoard();
  }

};
</script>

<style>
  .columns {
    list-style-type: none;
  }
</style>