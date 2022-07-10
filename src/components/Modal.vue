<template>
<div class="modal__container"></div>
  <div class="modal">
    <button 
      class="modal__close"
      @click="close"    
    >
      <img 
        src="@/assets/img/modClose.png" 
        alt="X"
      >
    </button>
    <div class="modal-info">
      <img 
        class="modal-info__photo"
        :src="info.photo" 
        alt="photo"
      >
      <div class="modal-info__data">
        <div class="modal-info__item">
          <p class="modal-info__name">Name:</p>
          <p class="modal-info__val">{{info.name}}</p>
        </div>

        <div class="modal-info__item">
          <p class="modal-info__name">Position:</p>
          <p class="modal-info__val">{{info.position}}</p>
        </div>

        <div class="modal-info__item">
          <p class="modal-info__name">Phone:</p>
          <p class="modal-info__val">{{info.phone}}</p>
        </div>

        <div class="modal-info__item">
          <p class="modal-info__name">Email:</p>
          <p class="modal-info__val">{{info.email}}</p>
        </div>
        <Social class="modal-info__social"/>
      </div>
    </div>
    <p class="description">{{info.description}}</p>
  </div>
</template>

<script>
import Social from './Social.vue';
export default {
  components: {Social},
  props: {
      info: {
          type: Object,
          required: true,
      }
  },
  data() {
      return {};
  },
  methods: {
      close() {
          this.$emit("closedModal");
          console.log("close");
      }
  }
}
</script>

<style lang="scss">
  .modal {
    z-index: 6;
    position: fixed;
    padding: 20px;
    width: 724px;
    height: 444px;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background: #FFFFFF;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.15);
    border-radius: 10px;
    &__container {
      z-index: 5;
      position: fixed;
      left: 0;
      top: 0;
      width: 100%;
      height: 100vh;
      background-color: #9A9A9A;
    }
    &__close {
      position: absolute;
      width: 36px;
      height: 36px;
      right: 0;
      margin-top: -36px;
      margin-right: -16px;
      background-color: #F8F8F8;
      border: 1px solid #DEDEDE;
      border-radius: 50%;
      cursor: pointer;
    }
  }
  .modal-info {
    display: flex;
    flex-direction: row;
    gap: 20px;
    &__photo {
      width: 271px;
      height: 239px;
      border: 1px solid #9A9A9A;
      border-radius: 5px;
    }
    &__data {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    &__item {
      display: flex;
      align-items: center;
    }
    &__name {
      width: 104px;
      font-weight: 400;
      font-size: 20px;
      line-height: 23px;
      color: #585858;
    }
    &__val {
      padding: 6px 10px;
      font-weight: 300;
      font-size: 20px;
      line-height: 23px;
      color: #2C2C2C;
      background-color: #F4F4F4;
      border-radius: 7px;
    }
    &__social > p {
      display: none;
    }
    // &__social > .social__box > a > img {
    //   color: #FF0B53;
    // }
    &__social {
      margin-top: 10px;
      width: 176px;
      height: 40px;
      background-color: #F4F4F4;
      border-radius: 7px;
      color: #2C2C2C;
    }
  }
  .description {
    margin-top: 20px;
    font-weight: 300;
    font-size: 20px;
    line-height: 147%;
    color: #3D3D3D;
  }
</style>
