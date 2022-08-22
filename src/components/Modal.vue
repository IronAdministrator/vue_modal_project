<script>
export default {
  props: ["headerText", "headerTitle", "theme"],
};
</script>

<template>
  <div class="backdrop">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1>{{ headerTitle }}</h1>
      <p>{{ headerText }}</p>
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
.modal.sale {
  background: black;
  color: white;
}
</style>
