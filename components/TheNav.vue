<template>
  <nav class="main-nav">
    <ul>
      <li v-for="page in pages" :key="page.id">
        <nuxt-link :to="page.href">
          {{ page.title }}
        </nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {
    pages: {
      type: Array,
      default: null,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.main-nav {
  position: relative;
  z-index: 10;

  ul {
    display: flex;
    align-items: center;
    flex-direction: row;

    li {
      color: white;
      font-weight: 600;
      font-size: 1.2rem;
      text-transform: uppercase;

      &:not(:first-child) {
        padding: 0 0 0 2rem;
      }

      a {
        color: inherit;
        text-decoration: none;
      }
    }
  }
}
</style>
