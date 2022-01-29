<template>
  <div class="container row">
    <div v-if="!error">
      <h3 class="page-title">Latest Posts</h3>
      <div class="latest-articles">
        <ArticleCard
          v-for="article in articles"
          :key="article.id"
          :image="article.content.image.filename"
          :title="article.content.title"
          :publish_date="article.first_published_at"
          :slug="article.full_slug"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ArticleCard from "./ArticleCard.vue";

export default {
  components: {
    ArticleCard,
  },
  props: {
    articles: {
      type: Array,
      default: null,
      required: false,
    },
    error: {
      type: String,
      default: null,
    },
  },
};
</script>

<style lang="scss" scoped>
.latest-articles {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  padding-top: 2rem;
}
</style>
