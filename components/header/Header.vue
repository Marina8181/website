<template>
  <header class="header">
    <div class="header__container">
      <div class="header__logo">
        <!-- Здесь будет логотип -->
        <img src="~/assets/pictures/logo.png" alt="Логотип" class="logo-img">
      </div>

      <Navigation />

      <div class="header__right">
        <Contact />
        <CallButton />
      </div>
    </div>
  </header>
</template>

<script>
import Navigation from './Navigation.vue'
import Contact from './Contact.vue'
import CallButton from './CallButton.vue'

export default {
  name: 'Header',
  components: {
    Navigation,
    Contact,
    CallButton
  }
}
</script>

<style scoped>
.header {
  background-color: #fff; /* или любой другой цвет по дизайну */
  padding: 20px 0;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.header__container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.header__logo {
  /* Стили для логотипа */
}

.header__right {
  display: flex;
  align-items: center;
  gap: 20px;
}

/* Здесь будут медиа-запросы для адаптива */
</style>