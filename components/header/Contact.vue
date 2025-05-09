<template>
  <div class="contact">
    <img src="~/assets/pictures/telephone.png" alt="телефон" class="img__phone">
    <a href="tel:+79009009090" class="contact__phone">+7 (900) 900-90-90</a>
  </div>
</template>

<script>
export default {
  name: 'Contact'
}
</script>

<style scoped>
.contact__phone {
  text-decoration: none;
  color: var(--color-number);
  font-family: var(--font-secondary);
  font-weight: var(--font-weight-normal);
  font-size: var(--font-secondary-size);
  line-height: var(--line-height-base);
}

.img__phone {
  margin-right: 8px;
}
</style>