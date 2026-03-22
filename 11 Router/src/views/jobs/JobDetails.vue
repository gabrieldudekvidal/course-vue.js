<template>
  <h1>Job Details</h1>
  <p>The job id is {{ id }}</p>
</template>

<script>
export default {
  // Receiving the id from Jobs.vue
  props: ["id"],
};
</script>

<style></style>
