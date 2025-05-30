<template>
  <footer class="footer">
    <div class="footer__grid">

      <div class="footer__logo-group">
        <img src="~/assets/pictures/logo2.png" alt="Логотип Загдом" class="footer__logo">
        <p class="footer__copyright">© Загдом, 2021</p>
      </div>

      <nav class="footer__nav">
        <ul class="footer__nav-list">
          <li class="footer__nav-item">
            <NuxtLink to="/projects" class="footer__link">Реализованные проекты</NuxtLink>
          </li>
          <li class="footer__nav-item">
            <NuxtLink to="/news" class="footer__link">Новости</NuxtLink>
          </li>
          <li class="footer__nav-item">
            <NuxtLink to="/contacts" class="footer__link">Контакты</NuxtLink>
          </li>
        </ul>
      </nav>

      <div class="footer__contacts-section">
        <div class="footer__contacts">
          <div class="footer__contact-item">
            <img src="~/assets/pictures/telephone.png" alt="телефон" class="footer__contact-icon">
            <address>+7 (900) 900-90-90</address>
          </div>
          <div class="footer__contact-item">
            <img src="~/assets/pictures/email.png" alt="почта" class="footer__contact-icon">
            <address>info@gmail.com</address>
          </div>
          <div class="footer__contact-item">
            <img src="~/assets/pictures/placeholder.png" alt="адрес" class="footer__contact-icon">
            <address>г. Владивосток ул. Выселковая 49, стр. 3</address>
          </div>
        </div>
      </div>

      <div class="footer__button-wrapper">
        <button class="footer__button">Оставить заявку</button>
      </div>

      <div class="footer__legal">
        <p class="footer__legal-item">Политика конфиденциальности</p>
        <p class="footer__legal-item">Пользовательское соглашение</p>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  background-color: #254741;
  color: white;
  padding: 40px 0;
  font-family: var(--font-secondary);
  font-size: var(--font-size-base);

  &__grid {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 40px;
    display: grid;
    grid-template-columns: auto 1fr auto;
    grid-template-rows: auto auto;
    grid-template-areas:
      "logo nav contacts button"
      "logo legal legal legal";
    gap: 30px 60px;
    align-items: start;
  }

  &__logo-group {
    grid-area: logo;
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  &__logo {
    width: 150px;
  }

  &__copyright {
    opacity: 0.6;
  }

  &__nav {
    grid-area: nav;
  }

  &__nav-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  &__link {
    color: white;
    text-decoration: none;
    transition: opacity 0.3s;

    &:hover {
      opacity: 1;
    }
  }

  &__contacts-section {
    grid-area: contacts;
    font-family: var(--font-primary);
    font-size: var(--font-secondary-size);
  }

  &__contacts {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  &__contact-item {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  &__contact-icon {
    width: 16px;
    height: 16px;
  }

  &__contact-item address {
    margin: 0;
    line-height: 1.5;
    white-space: nowrap;
  }

  &__button-wrapper {
    grid-area: button;
    display: flex;
    justify-content: flex-end;
  }

  &__button {
    background-color: #029F59;
    color: white;
    border: none;
    border-radius: 10px;
    padding: 10px 20px;
    cursor: pointer;
    font-family: var(--font-secondary);
    font-weight: var(--font-weight-normal);
    font-size: var(--font-secondary-size);
    line-height: var(--line-height-base);
    white-space: nowrap;
  }

  &__legal {
    grid-area: legal;
    display: flex;
    gap: 24px;
    opacity: 0.6;
    margin-top: 20px;
  }

  @media (max-width: 1024px) {
    &__grid {
      gap: 30px;
      grid-template-columns: auto 1fr auto;
      grid-template-areas:
        "logo nav contacts"
        "logo button button"
        "legal legal legal";
    }

    &__button-wrapper {
      justify-content: flex-start;
      margin-top: 20px;
    }
  }

  @media (max-width: 768px) {
    min-height: auto;
    padding: 40px 20px;

    &__grid {
      grid-template-columns: 1fr;
      grid-template-areas:
        "logo"
        "nav"
        "contacts"
        "button"
        "legal";
      gap: 40px;
    }

    &__legal {
      flex-direction: column;
      gap: 16px;
    }

    &__contact-item address {
      white-space: normal;
    }

    &__button {
      width: 100%;
    }
  }
}
</style>