<template>
  <div>
    <HeroBanner />
    <LatestArticles :articles="articles" />
  </div>
</template>

<script>
import HeroBanner from "~/components/HeroBanner.vue";
import LatestArticles from "~/components/LatestArticles.vue";
export default {
  components: {
    HeroBanner,
    LatestArticles,
  },
  data() {
    return {
      articles: [],
      error: null,
    };
  },
  async fetch() {
    this.$nuxt.context.app.$storyapi
      .get("cdn/stories", {
        starts_with: "articles/",
        resolve_relations: "author",
      })
      .then((response) => {
        response.data.stories.map((story) => {
          story.first_published_at = new Date(story.first_published_at);
          this.articles.push(story);
        });
      })
      .catch((error) => {
        this.error = error;
      });
  },
};
</script>

<style lang="scss" scoped></style>
