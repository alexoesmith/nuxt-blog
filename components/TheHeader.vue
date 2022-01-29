<template>
  <header>
    <div class="container header-wrap">
      <Logo />
      <TheNav :pages="pages" />
    </div>
  </header>
</template>

<script>
import { mapState } from "vuex";
import TheNav from "~/components/TheNav.vue";
import Logo from "~/components/Logo.vue";
export default {
  components: {
    Logo,
    TheNav,
  },
  computed: mapState({
    pages: (state) => state.pages.pages,
  }),
};
</script>

<style lang="scss" scoped>
header {
  padding: 1.4rem 1rem;
  background-color: $secondary;
  background-image: url("~/assets/images/contours.png");
  background-size: cover;
  background-position: center;
  position: relative;

  &:after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgb(0, 0, 0);
    background: linear-gradient(
      90deg,
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 0.6) 100%
    );
  }

  .header-wrap {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
