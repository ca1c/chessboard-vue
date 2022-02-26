<script>
import { defineComponent } from 'vue';
import ChessboardVue from '@/chessboard-vue.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    ChessboardVue
  }
});
</script>

<template>
  <div id="app">
    <chessboard-vue />
  </div>
</template>
