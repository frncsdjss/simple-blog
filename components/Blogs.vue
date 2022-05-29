<template>
  <div>
    <div class="flex py-3" v-for="blogs in data" :key="blogs.id">
      <img
        class="w-auto"
        :alt="blogs.metadata.description"
        :src="blogs.metadata.image.imgix_url + '?w=100'"
      />
      <h3 class="px-3">
        <NuxtLink :to="'/blog/' + blogs.slug"> {{ blogs.title }} </NuxtLink>
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  props: ['data'],
};
</script>

<style></style>
