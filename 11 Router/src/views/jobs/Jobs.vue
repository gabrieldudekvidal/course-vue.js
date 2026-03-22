<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
    <!-- The name refers to the component in the router/index.js -->
    <router-link :to="{ name: 'JobDetails', params: { id: job.id } }"
      ><h2>{{ job.title }}</h2></router-link
    >
  </div>
</template>

<script>
export default {
  name: "Jobs",
  data() {
    return {
      jobs: [
        { title: "UX Designer", id: 1, details: "lorem" },
        { title: "Web Developer", id: 2, details: "lorem" },
        { title: "Vue Developer", id: 3, details: "lorem" },
      ],
    };
  },
};
</script>

<style scoped>
h2 {
  background-color: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
  margin: 10px auto;
  max-width: 600px;
  cursor: pointer;
  color: #444;
}

h2:hover {
  background: #ddd;
}

a {
  text-decoration: none;
}
</style>
