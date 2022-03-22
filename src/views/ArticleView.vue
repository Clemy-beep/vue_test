<template>
  <p>{{ isLoading ? "Loading..." : "" }}</p>
  <article>
    <h1>{{ article.title }}</h1>
    <p>{{ article.content }}</p>
    <AuthorComponent v-bind:id="article.user_id"></AuthorComponent>
  </article>
</template>

<script language="ts">
import AuthorComponent from "../components/AuthorComponent.vue";

export default {
  watch: {},

  mounted() {
    this.fetchArticle();
  },
  components: { AuthorComponent },
  methods: {
    async fetchArticle() {
      let id = this.$route.params.id;
      await fetch(`/api/getArticle.php?id=${id}`).then((res) => {
        try {
          res.json().then((value) => {
            this.article = value[0];
            this.isLoading = false;
            return this.article;
          });
        } catch (error) {
          console.log(error);
        }
      });
    },
  },
  data() {
    return {
      article: this.fetchArticle(),
      isLoading: true,
    };
  },

  name: "ArticleView",
};
</script>
