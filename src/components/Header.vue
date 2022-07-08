<template>
  <div class="header">
    <div class="box header__box">
      <a href="/">
          <img class="header__logo" src="@/assets/img/logo.png" alt="logo">
      </a>
      <Menu />
    </div>
  </div>
</template>

<script>
import Menu from './Menu.vue';
export default {
    components: { Menu }
}
</script>

<style lang="scss">
  .header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #17191D;
    &__box {
      margin: 30px 0;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;

    }
    &__logo {
      width: 192px;
      height: 54px;
    }
  }
</style>
