<template>
  <div class="article">
    <h1>This is an articles list</h1>
    <div id="articles" v-for="(article, key) in articles" :key="key">
      <ArticleComponent :title="article.title" :content="article.content" ></ArticleComponent>
      <a href="http://localhost:8080/">Click me</a>
    </div>
  </div>
</template>

<script>
import ArticleComponent from "../components/ArticleComponent.vue";

const ArticlesList= [
  {
    title: "Hello",
    content: "Content"
  },
  {
    title: "Why",
    content: "Are u here ?"
  },
   {
    title: "I'm",
    content: "so much bored"
  },
];
export default {
  data () {
    return {
      articles: ArticlesList
    }
  },
  name: "ArticleList",
  components: {
    ArticleComponent,
  },
};
</script>
