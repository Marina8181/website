<template>
  <nav class="navigation">
    <ul class="navigation__list">
      <li class="navigation__item">
        <NuxtLink to="/projects" class="navigation__link">Реализованные проекты</NuxtLink>
      </li>
      <li class="navigation__item">
        <NuxtLink to="/news" class="navigation__link">Новости</NuxtLink>
      </li>
      <li class="navigation__item">
        <NuxtLink to="/contacts" class="navigation__link">Контакты</NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Navigation'
}
</script>

<style lang="scss">
.navigation {
  &__list {
    display: flex;
    flex-wrap: wrap; /* Добавлено для переноса элементов */
    align-items: center;
    gap: 30px;
    list-style: none;
    margin: 0;
    padding: 0;
    position: relative; /* Для позиционирования в адаптивном режиме */
  }

  &__item {
    position: relative;
    white-space: nowrap; /* Запрещаем перенос текста */
  }

  &__link {
    text-decoration: none;
    color: var(--color-text);
    font-family: var(--font-primary);
    font-weight: var(--font-weight-normal);
    font-size: var(--font-size-base);
    line-height: var(--line-height-base);
    transition: color 0.3s ease;

    &:hover {
      color: var(--color-primary);
    }
  }

  @media (max-width: 640px) {
    display: none; /* Полностью скрываем навигацию на мобильных */
  }
}
</style>
