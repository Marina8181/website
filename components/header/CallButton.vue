<template>
  <button class="call-button" @click="openModal">
    Оставить заявку
  </button>
</template>

<script>
export default {
  name: 'CallButton',
  methods: {
    openModal() {
      // Здесь будет логика открытия модального окна
      this.$emit('open-form');
    }
  }
}
</script>

<style scoped>
.call-button {
  padding: 10px 20px;
  background-color: #029F59;
  color: white;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  font-family: var(--font-secondary);
  font-weight: var(--font-weight-normal);
  font-size: var(--font-secondary-size);
  line-height: var(--line-height-base);
}
</style>