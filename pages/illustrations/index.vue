<template>
  <div class="container text-center page-top-padding">
    <h1 class="my-2">Images</h1>
    <section class="grid">
      <div class="grid__container">
        <figure v-for="(illustration, index) in illustrations" :key="index">
          <img
            :src="`https://ryjvicejickwdbxrtvmp.supabase.co/storage/v1/object/public/illustrations/${illustration.name}`"
            :alt="illustration.name"
          />
        </figure>
      </div>
    </section>
  </div>
</template>

<script>
import { useBooksStore } from "@/store/BooksStore";

export default {
  async setup() {
    const bookStore = useBooksStore();
    console.log(bookStore.illustrations);
    const illustrations = bookStore.illustrations
      ? bookStore.illustrations
      : await bookStore.getIllustrations();
    console.log(illustrations);

    return { illustrations };
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/main.scss";

.container {
  margin: 0 auto;
}
.grid {
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  width: 100%;

  &__container {
    max-width: 1024px;
    display: grid;
    grid-template-columns: 100%;
    @media (min-width: $mobile-lg) {
      grid-template-columns: 50% 50%;
    }
    @media (min-width: $tablet) {
      grid-template-columns: 33.333% 33.333% 33.333%;
    }

    figure {
      margin: 5px;
      padding: 5px;
    }

    img {
      display: block;
      max-width: 100%;
      height: 100%;
    }
  }
}
</style>