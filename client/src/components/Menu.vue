<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <ul class="nav mr-auto">
      <li class="nav-item menu-light__li">
        <router-link class="nav-link nav-link--light" :to="{ name: 'home' }">
          Главная
        </router-link>
      </li>
    </ul>
    <router-link class="nav-link nav-link--light" :to="{ name: 'admin' }">
      Админка
    </router-link>
    <router-link class="nav-link nav-link--light" :to="{ name: 'basket' }">
      В корзине: {{ totalItems }} Сумма:
      <span>{{ totalPrice | currency }}</span>
    </router-link>
  </nav>
</template>
<script>
export default {
  name: "Menu",
  computed: {
    totalItems() {
      return this.$store.state.totalItems;
    },
    totalPrice() {
      return this.$store.state.totalPrice;
    }
  }
};
</script>
<style lang="less">
.nav-link--light {
  color: #999;
}
</style>
