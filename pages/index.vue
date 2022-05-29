<template>
  <section class="footer container mx-auto py-40 px-3 font-serif">
    <div class="grid grid-cols-1">
      <div class="text-1xl">
        <h1>Getting All Blog Posts from Cosmicjs via Graphql</h1>
        <!-- <pre>{{ getObjects.objects }}</pre> -->
        <Blogs v-bind:data="getObjects.objects" />
        <pre>{{ getObjects }}</pre>
      </div>
    </div>
  </section>
</template>

<script>
import getObjects from '~/graphql/getObjects';

export default {
  apollo: {
    getObjects: {
      prefetch: true,
      query: getObjects,
    },
  },

  head() {
    return {
      title: 'Blog Index',
      desciption: 'This is page description',
    };
  },
};
</script>
