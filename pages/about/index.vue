<template>
  <div class="page-top-padding">
    <About />
  </div>
</template>

<script>
import About from "@/components/about/About";

export default {
  components: {
    About,
  },
  head() {
    return {
      title: "Sandra Plumb Books | About",
    };
  },
};
</script>

<style lang="scss" scoped>
.about-page__container {
  display: flex;
  align-items: center;
  flex: 1;
}
</style>
