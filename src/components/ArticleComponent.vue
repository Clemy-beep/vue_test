<template>
  <h2>{{ title }}</h2>
  <p>{{ content }}</p>
</template>

<script>
export default {
  name: "ArticleComponent",
  props: {
    title: String,
    content: String,
  },
};
</script>
