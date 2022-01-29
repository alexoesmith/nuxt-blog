<template>
  <article class="article-card">
    <div class="article-card__img">
      <img :src="image" />
      <span class="article-card__date">
        {{ publish_date.toLocaleDateString() }}
      </span>
    </div>
    <div class="article-card__content">
      <h3>{{ title }}</h3>
      <nuxt-link :to="slug">Read more</nuxt-link>
    </div>
  </article>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      default: null,
      required: true,
    },
    publish_date: {
      type: Date,
      default: null,
      required: true,
    },
    title: {
      type: String,
      default: null,
      required: true,
    },
    slug: {
      type: String,
      default: null,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.article-card {
  background: $primary;
  border-radius: $roundedCorners;
  overflow: hidden;

  &__img {
    height: 220px;
    position: relative;
    background-color: #ccc;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__date {
    position: absolute;
    top: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.8);
    backdrop-filter: blur(5px);
    padding: 0.4rem;
    font-size: 0.8rem;
    font-weight: bold;
    color: white;
    border-bottom-left-radius: $roundedCorners;
  }

  &__content {
    padding: 1.2rem;
    color: white;

    h3 {
      font-size: 1.4rem;
      font-weight: 600;
      padding-bottom: 0.4rem;
    }

    a {
      text-decoration: underline;
      font-weight: bold;
      color: $secondary;
    }
  }
}
</style>
