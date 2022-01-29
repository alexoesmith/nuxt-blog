<template>
  <section class="page-banner" :style="`background-image:url('${image}')`">
    <div class="container page-banner__inner">
      <div class="page-banner__content">
        <h1>{{ title }}</h1>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: null,
      required: true,
    },
    image: {
      type: String,
      default: null,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.page-banner {
  height: 500px;
  width: 100%;
  background-color: #ccc; // fallback
  background-size: cover;
  background-position: center;

  &__inner {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }

  &__content {
    h1 {
      display: inline-block;
      background-color: rgba(0, 0, 0, 0.6);
      color: white;
      font-size: 2rem;
      padding: 1.4rem;
      font-weight: bold;
    }
  }
}
</style>
