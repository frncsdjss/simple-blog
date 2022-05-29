<template>
  <section class="footer container mx-auto py-40 px-3 font-serif">
    <div class="grid grid-cols-1">
      <Blog v-bind:blogs="getObjects.objects" />
      <pre>{{ getObjects.objects }}</pre>
    </div>
  </section>
</template>

<script>
import getObjects from '~/graphql/getPost';

export default {
  data() {
    return {
      getObjects: [],
    };
  },
  apollo: {
    getObjects: {
      prefetch: true,
      query: getObjects,
      variables() {
        return {
          slug: this.$route.params.slug || '',
        };
      },
    },
  },
  head() {
    return {
      //this is not working
      title: '${this.blogs.title}',
    };
  },
};
</script>

<style></style>
