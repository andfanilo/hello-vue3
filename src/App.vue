<template>
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
  <button @click="toggleModalState">Open modal</button>
  <teleport to="#modal-wrapper">
    <modal v-if="modalOpen" @close="toggleModalState">
      <p>Hello, I'm a modal window.</p>
    </modal>
  </teleport>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Modal from "./components/Modal.vue";
import { ref } from "vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Modal,
  },
  setup() {
    const modalOpen = ref(false);
    const toggleModalState = () => {
      modalOpen.value = !modalOpen.value;
    };
    return {
      modalOpen,
      toggleModalState,
    };
  },
};
</script>
