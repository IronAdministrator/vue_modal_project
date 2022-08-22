<script>
import Modal from "@/components/Modal.vue";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My Vue App Title From Variable",
      headerText: "Sign Up!",
      headerTitle: "Modal Header",
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.inputText);
      this.$refs.inputText.classList.add("active");
    },
  },
};
</script>

<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="inputText" />
  <button @click="handleClick">click</button>
  <Modal :headerText="headerText" :headerTitle="headerTitle" theme="sale" />
</template>

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
