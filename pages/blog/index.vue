<template>
  <h1 class="text-3xl my-8">Developer Blogs</h1>

  I like to write blogs about my journey as a software developer. This section
  is sort of my Developer's Journal where I write about what I learned, bugs I
  have come acrossed and resolved, or neat information I'd like to share.

  <section class="grid md:grid-cols-3 mt-8 gap-10">
    <Post :posts="posts" />
  </section>
</template>

<script setup>
const { data: posts } = await useAsyncData("posts", () =>
  queryContent("/blog").find()
);
</script>
