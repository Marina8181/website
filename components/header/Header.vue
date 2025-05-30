<template>
  <header class="header">
    <div class="header__container">
      <div class="header__logo">
        <img src="~/assets/pictures/logo.png" alt="Логотип" class="logo-img">
      </div>

      <Navigation class="header__nav-desktop" />

      <div class="header__right-group">
        <Contact class="header__contact" />
        <CallButton class="header__call-button" @click="openModal" />
        <button
            class="header__burger"
            @click="toggleDrawer"
            :class="{ 'header__burger--active': isDrawerOpen }"
        >
          <span class="burger__line"></span>
          <span class="burger__line"></span>
          <span class="burger__line"></span>
        </button>
      </div>
      <Drawer :isOpen="isDrawerOpen" @close="isDrawerOpen = false" />
    </div>
    <Modal :isOpen="isModalOpen" @close="isModalOpen = false" />
  </header>
</template>

<script>
import Navigation from './Navigation.vue'
import Contact from './Contact.vue'
import CallButton from './CallButton.vue'
import Drawer from './Drawer.vue'
import Modal from '@/components/Modal.vue';

export default {
  name: 'Header',
  components: { Navigation, Contact, CallButton, Drawer, Modal },
  data() {
    return {
      isDrawerOpen: false,
      isModalOpen: false
    }
  },
  methods: {
    toggleDrawer() {
      this.isDrawerOpen = !this.isDrawerOpen
    },
    openModal() {
      this.isModalOpen = true;
    }
  }
}
</script>

<style scoped>
.header {
  background-color: #fff;
  padding: 20px 0;
  margin-bottom: 20px;
}

.header__container {
  display: flex;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  gap: 40px;
}

.header__logo {
  flex-shrink: 0;
}

.header__nav-desktop {
  display: flex;
  flex-grow: 1;
}

.header__right-group {
  display: flex;
  align-items: center;
  gap: 20px;
  flex-shrink: 0;
}

/* бургер */
.header__burger {
  display: none;
  background: #029F59;
  border: none;
  border-radius: 10px;
  padding: 10px;
  cursor: pointer;
  width: 40px;
  height: 40px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5px;
  margin-left: 15px;
  transition: all 0.3s ease;
}

.burger__line {
  display: block;
  width: 20px;
  height: 2px;
  background: white;
  transition: all 0.3s ease;
}

.header__burger--active {
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.header__burger--active .burger__line:nth-child(1) {
  transform: translateY(7px) rotate(45deg);
}

.header__burger--active .burger__line:nth-child(2) {
  opacity: 0;
}

.header__burger--active .burger__line:nth-child(3) {
  transform: translateY(-7px) rotate(-45deg);
}

@media (max-width: 1024px) {
  .header__nav-desktop .navigation__list {
    display: flex;
    flex-wrap: wrap;
    row-gap: 10px;
  }

  .header__nav-desktop .navigation__item:nth-child(1) { order: 1; }
  .header__nav-desktop .navigation__item:nth-child(2) { order: 2; }
  .header__nav-desktop .navigation__item:nth-child(3) {
    order: 4;
    width: 100%;
    text-align: left;
    padding-left: 0;
  }
}

@media (max-width: 768px) {
  .header__nav-desktop {
    gap: 0 30px;
  }

  .navigation__item:nth-child(2) {
    order: 3;
    width: 100%;
    padding-left: 0;
    margin-top: 10px;
  }

  .navigation__item:nth-child(3) {
    order: 4;
  }
}

@media (max-width: 640px) {
  .header__nav-desktop {
    display: none;
  }
}

@media (max-width: 480px) {
  .header__call-button {
    display: none;
  }
  .header__burger {
    display: flex;
  }
}

@media (max-width: 375px) {
  .header__contact {
    display: none;
  }

  .header__container {
    gap: 20px;
    justify-content: space-between;
  }
}
</style>
