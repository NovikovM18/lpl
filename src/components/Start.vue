<template>
  <div class="start">
    <div class="box start__box">
      <a href="#">
          <img class="start__logo" src="@/assets/img/logo.png" alt="logo">
      </a>
      <Menu class="start__desktop-menu"/>
      <MobileMenu />
      <div class="start__toogle">
        <img 
          class="start__toogle_open"
          src="@/assets/img/mmt.png" 
          alt="mmt"
          id="open"
          @click="mmOpen"
        >
        <img 
          class="start__toogle_close"
          src="@/assets/img/mmt_x.png" 
          alt="mmtx"
          id="close"
          @click="mmClose"
        >
      </div>
    </div>
    <div class="start__bgi"></div>
    <div class="start__c"></div>
    <div class="start__x1"></div>
    <div class="start__x2"></div>
  </div>
  <div 
     class="start__bb"
     id="bb"
  >
  </div>
</template>

<script>
import Menu from './Menu.vue';
import MobileMenu from './MobileMenu.vue';
export default {
  components: { Menu, MobileMenu },

  data() {
    return {

    }
  },
  methods: {
    mmOpen() {
        document.body.classList.add('hidden');
        document.getElementById('mm').classList.add('active-block');
        document.getElementById('bb').classList.add('active-block');
        document.getElementById('close').classList.add('active-block');
        document.getElementById('open').classList.add('deactive-block');
    },
    mmClose() {
        document.body.classList.remove('hidden');
        document.getElementById('mm').classList.remove('active-block');
        document.getElementById('bb').classList.remove('active-block');
        document.getElementById('close').classList.remove('active-block');
        document.getElementById('open').classList.remove('deactive-block');
    }
  }
}
</script>

<style lang="scss">
  .start {
    position: relative;
    width: 100%;
    height: 100vh;
    background-color: #17191D;
    overflow: hidden;
    &__box {
      position: absolute;
      top: 30px;
      left: 50%;
      transform: translate(-50%, 0);
      z-index: 5;
      margin: 0 auto;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    &__logo {
      width: 192px;
      height: 54px;
    }
    &__desktop-menu {
      @media (max-width: 768px) {
        display: none;
      }
    }
    &__toogle {
      width: 24px;
      height: 22px;
      position: relative;
      &:hover {
        cursor: pointer;
      }
      @media (min-width: 768px) {
        display: none;
      }
      &_open {
        position: absolute;
        transition: 500ms;
      }
      &_close {
        position: absolute;
        transform: translate(0, -2000%);
        transition: 500ms;
      }
    }
    &__bgi {
      position: absolute;
      top: 15vh;
      left: 0;
      width: 100%;
      height: 85vh;
      background-image: url('@/assets/img/start_bg.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
    }
    &__c {
      position: absolute;
      top: 52px;
      left: 22%;
      width: 256px;
      height: 256px;
      background-image: url('@/assets/img/start_c.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
      @media (max-width: 768px) {
        top: 112px;
        left: 24%;
      }
    }
    &__x1 {
      position: absolute;
      top: 70%;
      left: 10%;
      width: 148px;
      height: 148px;
      background-image: url('@/assets/img/start_x1.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
        @media (max-width: 768px) {
          display: none;
        }
    }
    &__x2 {
      position: absolute;
      top: 50%;
      right: 16px;
      transform: translate(0, -50%);
      width: 266px;
      height: 266px;
      background-image: url('@/assets/img/start_x2.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
    }
    &__bb {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100vh;
      backdrop-filter: blur(60px);
      transform: translate(0, -200%);
      transition: 500ms;
    }
  }
</style>
