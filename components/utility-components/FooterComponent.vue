<template>
  <footer class="footer">
    <div class="footer__left">
      <ul class="footer__list">
        <li class="footer__list--item">
          <nuxt-link to="/" class="footer__link">Home</nuxt-link>
        </li>
        <li class="footer__list--item">
          <nuxt-link to="/about" class="footer__link">About</nuxt-link>
        </li>
        <li class="footer__list--item">
          <nuxt-link to="/books" class="footer__link">Books</nuxt-link>
        </li>
        <li class="footer__list--item">
          <nuxt-link to="/reviews" class="footer__link">Reviews</nuxt-link>
        </li>
        <li class="footer__list--item">
          <nuxt-link to="/downloads" class="footer__link">Downloads</nuxt-link>
        </li>
        <li class="footer__list--item">
          <nuxt-link to="/illustrations" class="footer__link"
            >Illustrations</nuxt-link
          >
        </li>
      </ul>
      <div>
        <p class="footer__copyright">&copy; Sandra Plumb {{ year }}</p>
      </div>
    </div>
    <!-- <div class="footer__bottom"></div> -->
  </footer>
</template>

<script>
import "./scss/footer.scss";

export default {
  name: "FooterComponent",
  computed: {
    year() {
      return new Date().getFullYear();
    },
  },
};
</script>
