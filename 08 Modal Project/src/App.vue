<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to=".modals" v-if="showModal">
    <!-- Using the component and props to pass data. @close is activated by the emit event on Modal.vue.
    Using teleport to add this modal to .modals on public/index.html -->
    <Modal theme="sale" @close="toggleModal">
      <h1>Hello</h1>
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Modal Two</h1>
      <template v-slot:links>
        <a href="#">OK</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Show modal</button>
  <button @click="toggleModalTwo">Show modal Two</button>
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",
  components: { Modal } /* Using the modal component */,
  data() {
    return {
      title: "My First Vue App",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
