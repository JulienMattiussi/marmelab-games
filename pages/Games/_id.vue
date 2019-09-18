<template>
  <section class="container">
    <div>
      <img class="logo" alt="Logo" src="~assets/marmelab_games.png" />
      <h1 class="title">{{game.title}}</h1>
      <h2 class="subtitle">
        A game using
        <strong>{{game.language}}</strong> by
        <a target="_blank" :href="game.authorLink">
          <strong>{{game.author}}</strong>
        </a>
      </h2>
      <game :game="game" />
      <h2 class="subtitle">
        <a target="_blank" :href="game.repo">Download source here</a>
      </h2>
      <div class="links">
        <page-link href="/Games" title="All games" />
        <page-link href="/" title="Home" />
      </div>
    </div>
  </section>
</template>

<script>
import Game from "~/components/Game.vue";
import PageLink from "~/components/PageLink.vue";
import games from "~/data/games";

let game;

export default {
  components: {
    Game,
    PageLink
  },
  data() {
    const gameName = this.$nuxt.$route.params.id;
    game = games.find(game => game.name === gameName);
    return {
      game
    };
  }
};
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.logo {
  height: 120px;
  width: 120px;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
</style>
