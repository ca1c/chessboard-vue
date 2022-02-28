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
      files: ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'],
      ranks: ['8', '7', '6', '5', '4', '3', '2', '1'],
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