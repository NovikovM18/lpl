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
    <div class="start__modal">
      <h1 class="start__modal_title">Email marceting for fast-growing startups</h1>
      <p class="start__modal_p">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Id ut cursus dictum purus enim in in urna, suspendisse. Mauris, mollis sed sed ac.</p>
      <div class="start__modal_bb">
        <a 
          href="#contacts"
          class="start__modal_start"
        >
          Start Now
        </a>
        <a 
          href="#partners"
          class="start__modal_read"
        >
          Read More
        </a>
      </div>
    </div>
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
    return { }
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
    &__modal {
      position: absolute;
      width: 75%;
      height: auto;
      top:50%;
      left:50%;
      transform:translate(-50%, -50%);
      background: linear-gradient(104.93deg, rgba(122, 122, 122, 0.19) 1.86%, rgba(122, 122, 122, 0) 104.73%);
      filter: drop-shadow(0px 4px 4px rgba(50, 50, 50, 0.15));
      backdrop-filter: blur(100px);
      border-radius: 7px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 72px 40px;
        @media (max-width: 1124px) {
          padding: 56px 24px;
        }
        @media (max-width: 768px) {
          width: 90%;
        }
        @media (max-width: 360px) {
          width: 90%;
          padding: 36px 14px;
        }
      &_title {
        font-weight: 700;
        font-size: 72px;
        line-height: 83px;
        text-align: center;
        color: #FFF;
          @media (max-width: 1024px) {
            font-size: 34px;
            line-height: 39px;
          }
          @media (max-width: 360px) {
            font-size: 22px;
            line-height: 28px;
          }
      }
      &_p {
        margin-top: 40px;
        font-weight: 300;
        font-size: 24px;
        line-height: 28px;
        text-align: center;
        color: #FFF;
          @media (max-width: 1024px) {
            font-size: 16px;
            line-height: 20px;
          }
          @media (max-width: 360px) {
            font-size: 12px;
            line-height: 14px;
          }
      }
      &_bb {
        margin-top: 114px;
        display: flex;
        gap: 60px;
          @media (max-width: 1124px) {
            margin-top: 40px;
          }
          @media (max-width: 768px) {
            flex-direction: column;
            gap: 30px;
          }
          @media (max-width: 360px) {
            margin-top: 20px;
            gap: 20px;
          }
      }
      &_start {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 284px;
        height: 64px;
        background: #FF0B53;
        border-radius: 36px;
        text-decoration: none;
        font-weight: 400;
        font-size: 24px;
        line-height: 28px;
        color: #FBFBFB;
          @media (max-width: 1024px) {
            width: 240px;
            font-size: 20px;
            line-height: 23px;
          }
          @media (max-width: 360px) {
            width: 200px;
            font-size: 16px;
            line-height: 22px;
          }
      }
      &_read {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 284px;
        height: 64px;
        border: 1px solid #FFFFFF;
        border-radius: 36px;
        text-decoration: none;
        font-weight: 400;
        font-size: 24px;
        line-height: 28px;
        color: #FBFBFB;
          @media (max-width: 1024px) {
            width: 240px;
            font-size: 20px;
            line-height: 23px;
          }
          @media (max-width: 360px) {
            width: 200px;
            font-size: 16px;
            line-height: 22px;
          }
      }
    }
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
      @media (min-width: 769px) {
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
