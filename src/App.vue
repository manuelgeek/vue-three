<template>
  <h1>{{ appName }}</h1>
  <p>Base URL: {{ baseUrl }}</p>
  <button @click="toggleModalState">Open modal</button>
  <teleport to="#modal-wrapper">
    <modal v-if="modalOpen" @close="toggleModalState">
      <p>Hello, I'm a modal window.</p>
    </modal>
  </teleport>
</template>

<script>

import Modal from "./Modal";
import {ref} from "vue";

export default {
  name: 'App',
  components: {
    Modal
  },
  setup () {
    const modalOpen = ref(false);
    const toggleModalState = () => {
      modalOpen.value = !modalOpen.value;
    };
    const appName = process.env.VUE_APP_NAME;
    const baseUrl = process.env.VUE_APP_BASE_URL;
    return {
      modalOpen,
      toggleModalState,
      appName,
      baseUrl
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
