<script>
export default {
  props: ["text", "title", "theme"],
  methods: {
    closeModal() {
      this.$emit('close')
    },
  }
};
</script>

<template>
  <div @click.self="closeModal" class="backdrop">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot></slot>
      <div class="action-links">
        <slot name="links"></slot>
      </div>
      <slot name="modalTwo"></slot>
      <!-- <h1>{{ title }}</h1>-->
      <!-- <p>{{ text }}</p>-->
    </div>
  </div>
</template>

<style>
.backdrop {
  position: fixed;
  top: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.modal .action-links {
  text-align: center;
  margin: 2rem 0 .5rem 0;
}
.modal .action-links a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}
.modal.sale {
  background: lightseagreen;
  color: white;
}
.modal.sale .action-links a {
  color: white;
}
</style>
