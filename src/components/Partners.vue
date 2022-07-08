<template>
  <div class="partners">
    <div class="box partners__box">
      <h1 class="partners__title">Our Partners</h1>
      <div class="partners__content">
        <div class="big">
          <div class="big__info">
            <img 
              src="@/assets/img/pfib.png" 
              alt="photo" 
              class="big__img"
            >
            <div class="big__text">
              <p class="big__text_title">Tom Dou</p>
              <p class="big__text_p">Front-End</p>
            </div>
          </div>
          <p class="big__p">“Lorem ipsum dolor sit amet, consectetur adipiscing elit. At pretium id viverra interdum nam odio ultricies. Diam leo, sed neque dui pulvinar condimentum pretium. At pretium id viverra interdum nam odio ultricies. Diam leo, sed neque dui pulvinar condimentum pretium.”</p>
        </div>
        <div class="list">
          <div class="list__item">
            <img src="@/assets/img/p1.png" alt="logo"  class="list__item_img">
          </div>
          <div class="list__item">
            <img src="@/assets/img/p2.png" alt="logo"  class="list__item_img">
          </div>
          <div class="list__item">
            <img src="@/assets/img/p3.png" alt="logo"  class="list__item_img">
          </div>
          <div class="list__item">
            <img src="@/assets/img/p4.png" alt="logo"  class="list__item_img">
          </div>
          <div class="list__item">
            <img src="@/assets/img/p5.png" alt="logo"  class="list__item_img">
          </div>
          <div class="list__item">
            <img src="@/assets/img/p6.png" alt="logo"  class="list__item_img">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
  .partners {
    padding: 120px 0;
    background-color: #F8F8F8;
    @media (max-width: 768px) {
      padding: 50px 0;
    }
    &__box  {
      margin: 0 auto;
    }
    &__title {
      margin-bottom: 90px;
      font-weight: 700;
      font-size: 54px;
      line-height: 62px;
      color: #101020;
      @media (max-width: 768px) {
        margin-bottom: 40px;
      }
    }
    &__content {
      display: flex;
      @media (max-width: 768px) {
        flex-direction: column;
        gap: 20px;
      }
    }
  }
  .big {
    max-width: 860px;
    height: auto;
    padding: 30px;
    display: flex;
    flex-direction: column;
    gap: 30px;
    background-color: #fff;
    border: 1px solid #DEDEDE;
    box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
      @media (max-width: 768px) {
        width: 100%;
      }
    &__info {
      display: flex;
      gap: 15px;
    }
    &__img {
      width: 70px;
      height: 70px;
    }
    &__text {
      &_title {
        font-weight: 500;
        font-size: 24px;
        line-height: 28px;
        color: #000;
      }
      &_p {
        font-weight: 300;
        font-size: 20px;
        line-height: 23px;
        color: #575757;
      }
    }
    &__p {
      font-weight: 300;
      font-size: 20px;
      line-height: 147%;
      color: #3D3D3D;
    }
  }
  .list {
    margin-left: 10px;
    display: flex;
    align-items: start;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
      @media (max-width: 768px) {
        width: 100%;
        margin-left: 0;
      }
    &__item {
      width: 280px;
      height: 172px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #FFF;
      border: 1px solid #DEDEDE;
      border-radius: 10px;
      @media (max-width: 768px) {
        width: 160px;
        height: 100px;
      }
      &_img {
        width: 90%;
      }
    }
  }
</style>
