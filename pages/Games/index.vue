<template>
  <section class="container">
    <div>
      <img class="logo" alt="Logo" src="~assets/marmelab_games.png">
      <h1 class="title">All games list</h1>
      <h2 class="subtitle">Discover all production from Marmelab</h2>
      <div class="links">
        <a href="/" class="button--blue">Home</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  components: {}
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
  padding-top: 15px;
}
</style>
