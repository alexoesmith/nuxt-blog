<template>
  <div>
    <PageBanner
      :title="article.content.title"
      :image="article.content.image.filename"
    />
    <main class="page-pad">
      <div class="container">
        <div v-html="$md.render(article.content.content)"></div>
      </div>
    </main>
  </div>
</template>

<script>
import PageBanner from "~/components/PageBanner.vue";
export default {
  components: {
    PageBanner,
  },
  async asyncData({ app, route, error }) {
    const slug = route.params.slug;
    const res = await app.$storyapi.get("cdn/stories", {
      starts_with: "articles/",
      by_slugs: "*/" + slug,
      resolve_relations: "author",
    });
    const article = res.data.stories[0];
    if (!article) return error({ statusCode: 404 });
    article.content.date = new Date(article.content.date);
    return { article, author: article.content.author };
  },
};
</script>

<style lang="scss" scoped></style>
