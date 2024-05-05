<template>
  <section>
    <section>
      <h1 class="text-5xl font-bold mt-20">🤝 Greetings, I'm Edwin Khoo</h1>
      <p class="text-base text-gray-900 p-2 italic">
        Bachelor of Software Engineering (Honours) Undergraduate,
        <br />
        Software Engineer Intern at Finexus International Sdn Bhd
      </p>
    </section>
    <section class="flex flex-col md:flex-row">
      <div class="md:w-1/2">
        <h2 class="text-3xl font-bold mt-20">About Me</h2>
        <p class="text-base text-gray-900">
          I am a fresh graduate and a relative newbie in the software
          development space. I have previous experience in web development and
          data science from my internship and personal projects.
          <br />
          <br />
          Aside from exposure to the space from my tertiary education and side
          projects, I also spend some of my free time everyday to read tech
          articles, blogs and videos to keep myself up to date on the latest
          tech trends.
          <br />
        </p>
      </div>
      <img
        src="~/assets/images/ProfilePhoto.png"
        class="w-1/2 md:max-w-sm mx-auto"
      />
    </section>

    <section>
      <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
      <div class="grid md:grid-cols-3 pt-8 gap-10">
        <Post :posts="posts" />
      </div>
    </section>
  </section>
</template>

<script setup>
const { data: posts } = await useAsyncData("latest-posts", () =>
  queryContent("/blog").sort({ date: -1 }).limit(3).find()
);
</script>

<style lang="scss" scoped></style>
