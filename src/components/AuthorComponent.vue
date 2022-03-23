<template>
  <p>Written by : {{ author.name ?? "Anonymous author" }}</p>
</template>

<script>
export default {
  props: {
    id: String,
  },
  name: "AuthorComponent",
  data() {
    return {
      author: {},
    };
  },
  methods: {
    async fetchAuthor() {
      await fetch(`/api/getUser.php?id=${this.id}`).then((res) => {
        try {
          res.json().then((value) => {
            this.author = value;
            return this.author;
          });
        } catch (error) {
          console.warn(error);
        }
      });
    },
  },
};
</script>
