<template>
  <button @click="toggleModalState">Open modal</button>
  <modal v-if="modalOpen">
    <p>Hello, I'm a modal window.</p>
  </modal>
</template>

<script>

import Modal from "./Modal";

export default {
  name: 'App',
  components: {
    Modal
  },
  data: () => ({
    modalOpen: true
  }),
  methods: {
    toggleModalState() {
      this.modalOpen = !this.modalOpen;
    }
  }
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
