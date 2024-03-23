<script setup>
const query = gql`
  {
    viewer {
      repositories(first: 6, orderBy: { field: CREATED_AT, direction: DESC }) {
        totalCount
        nodes {
          id
          name
          createdAt
          updatedAt
          description
          url
        }
      }
    }
  }
`;

const { data } = await useAsyncQuery(query);
</script>

<template>
  <h1 class="text-3xl my-8">Projects</h1>
  <p class="text-lg mb-8">Here are some of my projects on GitHub.</p>
  <section class="grid grid-cols-2 gap-10">
    <div
      v-for="project in data?.viewer.repositories.nodes"
      :key="project.id"
      class="p-8 border-4 my-4 rounded-lg hover:bg-gray-50"
    >
      <a :href="project.url" target="_blank">
        <h2 class="text-2xl text-indigo-800 font-semibold mb-2 hover:underline">
          {{ project.name }}
        </h2>
      </a>
      <p>{{ project.description }}</p>
    </div>
  </section>
</template>
