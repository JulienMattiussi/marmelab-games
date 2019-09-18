<template>
  <div class="link">
    <a
      :href="href"
      :class="extern ? 'button--grey' : 'button--blue'"
      :target="extern ? '_blank' : '_self'"
    >{{title}}</a>
  </div>
</template>

<script scoped>
export default {
  name: "PageLink",
  props: {
    href: String,
    title: String,
    extern: Boolean
  }
};
</script>

<style scoped>
.link {
  width: 150px;
  padding-top: 15px;
  padding-bottom: 15px;
}
</style>
