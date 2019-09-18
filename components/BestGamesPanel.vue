<template>
  <div class="panel">
    <div v-for="game in getBests(games, maxNumber)" :key="game.name">
      <game-thumb :game="game" />
    </div>
  </div>
</template>

<script scoped>
import GameThumb from "./GameThumb.vue";
export default {
  components: {
    GameThumb
  },
  name: "BestGamesPanel",
  props: {
    games: Array,
    maxNumber: Number
  },
  methods: {
    getBests(games, maxNumber) {
      return games.filter((game, idx) => idx < (maxNumber || 5));
    }
  }
};
</script>

<style scoped>
.panel {
  display: flex;
  flex-direction: row;
  justify-content: center;
  height: 180px;
}
</style>
