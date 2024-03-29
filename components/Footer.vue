<template>
  <footer class="bg-slate-600">
    <section
      class="mx-auto max-w-7xl px-2 sm:px-4 lg:py-6 text-gray-300 flex flex-row"
    >
      <p class="flex-1">
        &copy; Developed by Khoo Ed Win 2024 | &reg; All Rights Reserved
      </p>
      <div class="flex flex-row justify-center gap-4 mb-4 mt-2">
        <Icon name="mi:email" :style="{ fontSize: '30px' }"></Icon>
        <p>edwin9938@gmail.com</p>
        <a v-for="link in links" :key="link.name" :href="link.href">
          <Icon :name="link.icon" size="1.5rem" class="text-gray-300" />
        </a>
      </div>
    </section>
  </footer>
</template>

<script setup>
const links = [
  {
    name: "GitHub",
    href: "https://github.com/Edwin-Kh",
    icon: "grommet-icons:github",
  },
  {
    name: "LinkedIn",
    href: "https://www.linkedin.com/in/edwin-khoo2002/",
    icon: "mdi:linkedin",
  },
];
</script>

<style lang="scss" scoped></style>
