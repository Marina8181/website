<template>
  <transition name="modal-fade">
    <div v-if="isOpen" class="modal">
      <div class="modal__backdrop" @click="close"></div>

      <div class="modal__container">
        <button class="modal__close" @click="close">
          <svg viewBox="0 0 24 24">
            <path d="M18 6L6 18"/>
            <path d="M6 6l12 12"/>
          </svg>
        </button>

        <div class="modal__content">
          <p class="modal__title">Оставить заявку</p>
          <p class="modal__text">Появится позже</p>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    isOpen: Boolean
  },
  methods: {
    close() {
      this.$emit('close');
    }
  },
  watch: {
    isOpen(val) {
      document.body.style.overflow = val ? 'hidden' : 'auto';
    }
  }
}
</script>

<style lang="scss" scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1100;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  font-family: var(--font-secondary);
  font-size: var(--font-size-big);
  font-weight: var(--font-weight-bold);

  &__backdrop {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
  }

  &__container {
    position: relative;
    background: white;
    border-radius: 12px;
    padding: 40px;
    max-width: 500px;
    width: 100%;
    z-index: 1101;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
  }

  &__close {
    position: absolute;
    top: 20px;
    right: 20px;
    width: 40px;
    height: 40px;
    border-radius: 8px;
    border: 1px solid rgba(2, 159, 89, 0.3);
    background: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s;

    &:hover {
      background: rgba(2, 159, 89, 0.1);
    }

    svg {
      width: 16px;
      height: 16px;
      stroke: #029F59;
      stroke-width: 2;
    }
  }

  &__title {
    margin-bottom: 20px;
  }

  &__text {
    color: #666;
  }
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.3s ease;
}

.modal-fade-enter,
.modal-fade-leave-to {
  opacity: 0;
}
</style>