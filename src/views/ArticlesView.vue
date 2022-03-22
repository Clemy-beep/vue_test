<template>
  <div class="article">
    <h1>This is an articles list</h1>
    <p>{{ isLoading ? "Loading..." : "" }}</p>
    <div id="articles" v-for="(article, key) in articles" :key="key">
      <ArticleComponent
        :title="article.title"
        :content="article.content"
      ></ArticleComponent>
      <router-link :to="{ name: 'article', params: { id: article.id } }"
        >Click me</router-link
      >
    </div>
    <h3 :class="{ isClicked: clicked }" @click="makeMeRed">I'm black</h3>
  </div>
</template>

<script language="ts">
import ArticleComponent from "../components/ArticleComponent.vue";

export default {
  watch: {},
  mounted() {
    this.fetchArticles();
  },
  data() {
    return {
      articles: this.fetchArticles(),
      clicked: false,
      isLoading: true,
    };
  },
  name: "ArticleList",
  components: {
    ArticleComponent,
  },
  methods: {
    makeMeRed: function () {
      this.clicked = !this.clicked;
    },
    fetchArticles: async function () {
      await fetch("/api/getArticles.php").then((res) => {
        try {
          res.json().then((value) => {
            this.articles = value;
            this.isLoading = false;
            return value;
          });
        } catch (e) {
          console.warn(e);
        }
      });
    },
  },
};
</script>

<style scoped>
h3 {
  color: blueviolet;
  cursor: pointer;
}
.isClicked {
  color: red;
}

.loading {
  display: none;
}
</style>
