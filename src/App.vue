<template>
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
  <button @click="toggleModalState">Open modal</button>
  <modal v-if="modalOpen">
    <p>Hello, I'm a modal window.</p>
  </modal>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Modal,
  },
  data: () => ({
    modalOpen: false,
  }),
  methods: {
    toggleModalState() {
      this.modalOpen = !this.modalOpen;
    },
  },
};
</script>
