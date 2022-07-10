<template>
  <div class="social">
    <div class="social__box">
      <a href="" class="social__item">
        <img src="@/assets/img/facebook-box-line.png" alt="icon" target="_blank">
      </a>
      <a href="" class="social__item">
        <img src="@/assets/img/twitter-line.png" alt="icon" target="_blank">
      </a>
      <a href="" class="social__item">
        <img src="@/assets/img/linkedin-box-line.png" alt="icon" target="_blank">
      </a>
      <a href="" class="social__item">
        <img src="@/assets/img/instagram-line.png" alt="icon" target="_blank">
      </a>
    </div>
    <p class="social__text">Privacy Policy</p>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
  .social {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 24px;
    &__box {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 16px;
    }
    &__item {
      width: 30px;
      height: 30px;
    }
    &__text {
      font-weight: 300;
      font-size: 16px;
      line-height: 18px;
      color: #B1B1B1;
    }
  }
</style>