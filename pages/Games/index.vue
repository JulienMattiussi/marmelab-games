<template>
  <section class="container">
    <div>
      <img class="logo" alt="Logo" src="~assets/marmelab_games.png" />
      <h1 class="title">All games list</h1>
      <h2 class="subtitle">Discover all production from Marmelab</h2>
      <div class="display-row">
        <dropdown
          name="Choose a game"
          :items="getGames(games)"
          :changeFilter="setFilter(filters, 'gameName')"
        />
        <dropdown
          name="Choose an author"
          :items="getAuthors(games)"
          :changeFilter="setFilter(filters, 'author')"
        />
        <dropdown
          name="Choose a language"
          :items="getLanguages(games)"
          :changeFilter="setFilter(filters, 'language')"
        />
      </div>
      <div class="games-panel">
        <div v-for="game in current(games, filters)" :key="game.name">
          <game-thumb :game="game" />
        </div>
      </div>
      <div class="display-row">
        <page-link href="/" title="Home" />
      </div>
    </div>
  </section>
</template>

<script>
import GameThumb from "~/components/GameThumb.vue";
import PageLink from "~/components/PageLink.vue";
import Dropdown from "~/components/Dropdown.vue";
import games from "~/data/games";
export default {
  components: {
    GameThumb,
    PageLink,
    Dropdown
  },
  data() {
    return {
      games,
      filters: {
        gameName: null,
        author: null,
        language: null
      }
    };
  },
  methods: {
    current(games, filters) {
      if (!filters || Object.keys(filters).length === 0) {
        console.log(filters);
        return games;
      }
      return games.filter(game => {
        return Object.keys(filters).every(
          filter => filters[filter] == null || filters[filter] === game[filter]
        );
      });
    },
    setFilter(filters, filter) {
      return value => {
        filters[filter] = value;
      };
    },
    getGames(games) {
      return [...new Set(games.map(game => game.gameName).sort())];
    },
    getAuthors(games) {
      return [...new Set(games.map(game => game.author).sort())];
    },
    getLanguages(games) {
      return [...new Set(games.map(game => game.language).sort())];
    }
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

.games-panel {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
  width: 1000px;
}

.display-row {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
</style>
