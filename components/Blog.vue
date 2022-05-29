<template>
  <div class="text-1xl">
    <div v-for="blog in blogs" :key="blog.id">
      <img class="w-full" :src="blog.metadata.image.imgix_url + '?w=600'" />
      <h1>{{ blog.title }}</h1>
      <p class="blog-description inline text-xl" v-html="blog.content"></p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["blogs"],
  layout: "default",
};
</script>

<style></style>
