<template>
  <div class="mm">
    <Menu />
    <Social />
  </div>
</template>

<script>
import Menu from './Menu.vue';
import Social from './Social.vue';

export default {
  components: { Menu, Social },
}
</script>

<style lang="scss">
.mm {
  position: absolute;
  width: 100%;
  height: 75vh;
  top: 15vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  &__menu {
    display: flex;
    flex-direction: column;
  }
}
</style>