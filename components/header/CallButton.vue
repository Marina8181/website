<template>
  <button class="call-button" @click="handleClick">
    Оставить заявку
  </button>
</template>

<script>
export default {
  name: 'CallButton',
  methods: {
    handleClick() {
      this.$emit('open-modal');
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
