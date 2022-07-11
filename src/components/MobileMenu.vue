<template>
  <div class="mm" id="mm">
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
  z-index: 30;
  width: 100%;
  height: 75vh;
  top: 15vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transform: translate(0, -200%);
  transition: 500ms;
  &__menu {
    display: flex;
    flex-direction: column;
  }
}
</style>