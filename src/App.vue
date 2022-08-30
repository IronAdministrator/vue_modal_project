<script>
import Modal from "@/components/Modal.vue";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My Vue App Title From Variable",
      modalText: "Sign Up!",
      modalTitle: "Modal Header",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.inputText);
      this.$refs.inputText.classList.add("active");
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    }
  },
};
</script>

<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="inputText" />
  <button @click="handleClick">click</button>
  <p>Welcome!</p>
  <div v-if="showModal">
    <!-- <Modal :text="modalText" :title="modalTitle" theme="sale" @close="toggleModal" />-->
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">more info</a>
        <a href="#">even more info</a>
      </template>
      <h1>{{modalTitle}}</h1>
      <p>{{modalText}}</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:modalTwo>
        <h1>This is the Second Modal Title</h1>
        <p>This is the Second Modal Content</p>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">openModal</button>
  <button @click="toggleModalTwo">openModalTwo</button>
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
