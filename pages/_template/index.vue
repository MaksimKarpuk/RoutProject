<template></template>

<script>
import content from "../../assets/content.json";
export default {
  validate({ params }) {
    return Object.keys(content.pages).includes(params.template);
  },
  mounted() {
    console.log(this.$route.params);
  },
  asyncData({ params }) {
    return {
      title: content.pages[params.template].title,
    };
  },
  head() {
    return {
      title: this.title,
    };
  },
};
</script>

<style>
</style>