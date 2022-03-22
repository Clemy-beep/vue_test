<template>
  <div class="container">
    <h2>{{ title }}</h2>
    <p>{{ content }}</p>
  </div>
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

<style scoped>
.container {
  color: #2c3e50;
  border: 1px solid black;
  width: fit-content;
  display: block;
  margin: 1em auto;
  padding: 0.5em;
  border-radius: 16px;
  text-overflow: ellipsis;
}
p {
  max-height: 110px;
  overflow: hidden;
}
</style>
