<template>
  <section class="container">
    <div>
      <marmelab-logo/>
      <h1 class="title">Marmelab games</h1>
      <h2 class="subtitle">Discover Marmelab's entertainment production</h2>
      <best-games-panel :games="games"/>
      <div class="links">
        <a href="Games" class="button--blue">All games</a>
        <a href="https://marmelab.com/" target="marmelab" class="button--grey">Main site</a>
      </div>
    </div>
  </section>
</template>

<script>
import MarmelabLogo from "~/components/MarmelabLogo.vue";
import BestGamesPanel from "~/components/BestGamesPanel.vue";
import games from "~/data/games";

export default {
  components: {
    MarmelabLogo,
    BestGamesPanel
  },
  data() {
    return { games };
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
  padding-top: 15px;
}
</style>
