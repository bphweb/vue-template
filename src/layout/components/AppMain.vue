<template>
  <section class="app-main">
    <transition name="fade" mode="out-in">
      <keep-alive :include="cachedViews">
        <router-view :key="key"></router-view>
      </keep-alive>
    </transition>
  </section>
</template>

<script>
export default {
  name: "AppMain",
  computed: {
    cachedViews() {
      return this.$store.state.tagsView.cachedViews;
    },
    key() {
      return this.$route.fullPath;
    },
  },
};
</script>
