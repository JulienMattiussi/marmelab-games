<template>
  <div class="card">
    <a class="link" :href="`/Games/${game.name}`" :title="`by ${game.author}`">
      <img class="preview" :alt="game.title" :src="getImage(game.previewName)" />
      <span class="previewTitle">{{game.title}}</span>
    </a>
  </div>
</template>

<script scoped>
export default {
  name: "GameThumb",
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
.card {
  border-radius: 4px;
  border: 1px solid #33549d;
  color: #33549d;
  height: 170px;
  width: 120px;
  text-decoration: none;
  margin: 5px;
  overflow: hidden;
}

.link {
  text-decoration: none;
  display: flex;
  flex-direction: column;
}

.preview {
  height: 119px;
  width: 119px;
}

.previewTitle {
  padding-top: 10px;
  height: 45px;
  color: black;
  font-weight: bold;
}

.card:hover {
  background-color: rgb(51, 84, 157);
  opacity: 0.5;
}

.card:hover .previewTitle {
  color: #fff;
}
</style>
