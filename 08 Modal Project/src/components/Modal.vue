<template>
  <div class="backdrop" @click.self="closeModal">
    <!-- If the value of theme is sale add the sale class -->
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <!-- Using the data passed from the slot -->
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
        <!-- named slot -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"] /* Setting the prop */,
  methods: {
    closeModal() {
      /* Emit an event to the App.vue */
      this.$emit("close");
    },
  },
};
</script>

<style>
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
  border: none;
  padding: 0;
}

p {
  font-style: normal;
}

.actions {
  text-align: center;
  margin: 30px 0 10px 0;
}

.actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}

.sale {
  background-color: crimson;
  color: #fff;
}

.sale h1 {
  color: #fff;
}

.modal.sale .actions {
  color: #fff;
}

.modal.sale .actions a {
  color: #fff;
}
</style>
