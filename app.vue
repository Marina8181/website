<template>
  <div class="layout">
    <Header @toggle-drawer="isDrawerOpen = $event" />
    <main class="content">
      <Main />
      <NuxtPage />
    </main>
    <Footer />
    <Modal :isOpen="isModalOpen" @close="isModalOpen = false" />
    <Drawer :isOpen="isDrawerOpen" @close="isDrawerOpen = false" />
  </div>
</template>

<script>
import Header from '~/components/header/Header.vue'
import Footer from '~/components/Footer.vue'
import Modal from '~/components/Modal.vue'
import Drawer from '~/components/header/Drawer.vue'
import '@csstools/normalize.css'

export default {
  components: { Header, Footer, Modal, Drawer },
  data() {
    return {
      isModalOpen: false,
      isDrawerOpen: false
    }
  }
}
</script>

<style>
html, body {
  height: 100%;
  margin: 0;
  padding: 0;
}

.layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  position: relative;
}

.content {
  flex: 1 0 auto; /* Растягиваем контент на всё доступное пространство */
}

body.no-scroll {
  overflow: hidden; /* Блокировка прокрутки при открытых модальных окнах */
}

</style>
