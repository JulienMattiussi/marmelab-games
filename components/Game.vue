<template>
  <div class="game">
    {{game.title}}
    <br>
    <br>TODO
    <br>
    <br>Game link or game playable inside (depends of the game language
  </div>
</template>

<script scoped>
export default {
  name: "Game",
  props: {
    game: Object
  }
};
</script>

<style scoped>
.game {
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  border: 1px solid #33549d;
  height: 500px;
  width: 700px;
}
</style>
