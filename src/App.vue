<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <!-- Template Refs: we use them instead of grabbing elements from the DOM via document.getElementById(...) or document.querySelector(...) -->
  <!--
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button> -->
  <div v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme='sale' @close="toggleModal"/> -->
    <Modal theme='sale' @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now!</a>
        <a href="#">More Info</a>
      </template> 
    <!-- pass in a template ($slot) -->
      <h1>Ninja Givaway</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">open modal (alt)</button>
</template>

<script>

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data () {
    return {
      title: 'My First Vue App :)',
      header: 'Sign up for the Giveaway!',
      text: 'Grab your ninja swag for half price!',
      showModal: false,
    }
  },
  methods: {
    /*
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }, */
    toggleModal() {
      this.showModal = !this.showModal

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
