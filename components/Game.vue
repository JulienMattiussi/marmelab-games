<template>
  <div class="game">
    <h2>{{game.title}}</h2>
    <div class="visual">
      <img class="preview" :alt="game.title" :src="getImage(game.previewName)" />
    </div>
  </div>
</template>

<script scoped>
export default {
  name: "Game",
  props: {
    game: Object
  },
  methods: {
    getImage(imageName) {
      return require(`~/assets/previews/${imageName}`);
    }
  }
};
</script>

<style scoped>
.game {
  margin: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  border: 1px solid #33549d;
  height: 500px;
  width: 700px;
}
.visual {
  height: 400px;
}

.preview {
  object-fit: fill;
  max-height: 400px;
  max-width: 700px;
}
</style>
