<template>
  <transition name="slide">
    <div v-if="isOpen" class="drawer">
      <div class="drawer__backdrop" @click="close"></div>

      <div class="drawer__content">
        <button class="drawer__close" @click="close">
          <span class="drawer__close-line"></span>
          <span class="drawer__close-line"></span>
        </button>

        <nav class="drawer__nav">
          <NuxtLink to="/projects" class="drawer__link" @click.native="close">Реализованные проекты</NuxtLink>
          <NuxtLink to="/news" class="drawer__link" @click.native="close">Новости</NuxtLink>
          <NuxtLink to="/contacts" class="drawer__link" @click.native="close">Контакты</NuxtLink>
        </nav>

        <div class="drawer__contacts">
          <div class="drawer__contact-item">
            <img src="~/assets/pictures/telephone.png" alt="Телефон" class="drawer__contact-icon">
            <a href="tel:+79009009090">+7 (900) 900-90-90</a>
          </div>
          <div class="drawer__contact-item">
            <img src="~/assets/pictures/email.png" alt="Email" class="drawer__contact-icon">
            <a href="mailto:info@gmail.com">info@gmail.com</a>
          </div>
          <div class="drawer__contact-item">
            <img src="~/assets/pictures/placeholder.png" alt="Адрес" class="drawer__contact-icon">
            <span>г. Владивосток<br>ул. Выселковая 49, стр. 3</span>
          </div>
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
  watch: {
    isOpen(val) {
      document.body.style.overflow = val ? 'hidden' : 'auto'
    }
  },
  methods: {
    close() {
      this.$emit('close')
    }
  }
}
</script>

<style lang="scss" scoped>
.drawer {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1000;
  display: flex;
  justify-content: flex-end;
  font-family: var(--font-primary);
  font-size: var(--font-size-base);
  font-weight: var(--font-weight-normal);

  &__backdrop {
    position: absolute;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
  }

  &__content {
    position: relative;
    width: 320px;
    height: 100%;
    background: #029F59;
    padding: 30px;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    z-index: 1001;
  }

  &__close {
    position: absolute;
    top: 20px;
    right: 20px;
    width: 40px;
    height: 40px;
    background: none;
    border: 1px solid rgba(255, 255, 255, 0.3);
    border-radius: 10px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;

    &-line {
      display: block;
      width: 20px;
      height: 2px;
      background: white;
      position: absolute;

      &:first-child {
        transform: rotate(45deg);
      }
      &:last-child {
        transform: rotate(-45deg);
      }
    }
  }

  &__nav {
    display: flex;
    flex-direction: column;
    gap: 25px;
    margin-top: 50px;
  }

  &__link {
    color: white;
    text-decoration: none;
    font-size: 18px;
    font-weight: 500;
    transition: opacity 0.3s;

    &:hover {
      opacity: 0.8;
    }
  }

  &__contacts {
    margin-top: auto;
    padding-top: 40px;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  &__contact-item {
    display: flex;
    align-items: center;
    gap: 12px;
    font-family: var(--font-secondary);
    font-size: var(--font-secondary-size);

    a, span {
      color: white;
      opacity: 0.8;
      text-decoration: none;
      line-height: 1.4;
    }
  }

  &__contact-icon {
    width: 18px;
    height: 18px;
    opacity: 0.8;
  }
}

.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.3s;

  .drawer__content {
    transition: transform 0.3s ease;
  }
}

.slide-enter,
.slide-leave-to {
  opacity: 0;

  .drawer__content {
    transform: translateX(100%);
  }
}
</style>