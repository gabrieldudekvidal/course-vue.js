<template>
  <div class="backdrop" @click="closeModal">
    <!-- If the value of theme is sale add the sale class -->
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <!-- Using the data passed from the prop -->
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"] /* Setting the prop */,
  methods: {
    closeModal() {
      /* Emit an event to the App.vue */
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
/* Use scoped style for specific components */
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: #fff;
  border-radius: 10px;
}

.backdrop {
  top: 0;
  left: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

h1 {
  color: #03cfb4;
  border: none;
  padding: 0;
}

.sale {
  background-color: crimson;
  color: #fff;
}

.sale h1 {
  color: #fff;
}
</style>
