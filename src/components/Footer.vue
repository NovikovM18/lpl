<template>
  <div class="footer">
    <div class="footer__g"></div>
    <div class="box footer__box">
      <h1 class="footer__title">Where You Can Find Us?</h1>
      <div class="footer__content">
        <div class="content__box">
          <h2 class="content__title">Office 1</h2>
          <hr>
          <a class="content__info" href="https://goo.gl/maps/vgG6TthQxULjPBZUA" target="_blank">
            <img class="content__info_img" src="@/assets/img/map-pin-2-line.svg" alt="icon">
            <p class="content__info_p">Lasnamae linnaosa, Pae tn 25-47</p>
          </a>
          <a class="content__info" href="mailto:username@mail.com" target="_blank">
            <img class="content__info_img" src="@/assets/img/mail-line.svg" alt="icon">
            <p class="content__info_p">username@mail.com</p>
          </a>
          <a class="content__info" href="tel:+3125789075" target="_blank">
            <img class="content__info_img" src="@/assets/img/phone-line.svg" alt="icon">
            <p class="content__info_p">+3125789075</p>
          </a>
        </div>

        <div class="content__box">
          <h2 class="content__title">Office 2</h2>
          <hr>
          <a class="content__info" href="https://goo.gl/maps/vgG6TthQxULjPBZUA" target="_blank">
            <img class="content__info_img" src="@/assets/img/map-pin-2-line.svg" alt="icon">
            <p class="content__info_p">Lasnamae linnaosa, Pae tn 25-47</p>
          </a>
          <a class="content__info" href="mailto:username@mail.com" target="_blank">
            <img class="content__info_img" src="@/assets/img/mail-line.svg" alt="icon">
            <p class="content__info_p">username@mail.com</p>
          </a>
          <a class="content__info" href="tel:+3125789075" target="_blank">
            <img class="content__info_img" src="@/assets/img/phone-line.svg" alt="icon">
            <p class="content__info_p">+3125789075</p>
          </a>
        </div>

        <div class="content__box">
          <h2 class="content__title">Socials</h2>
          <hr>
          <div class="content__social_box">
            <div class="content__social">
              <a href="" class="content__social_item">
                <img class="content__social_img" src="@/assets/img/1.svg" alt="icon" target="_blank">
              </a>
              <a href="" class="content__social_item">
                <img class="content__social_img" src="@/assets/img/3.svg" alt="icon" target="_blank">
              </a>
              <a href="" class="content__social_item">
                <img class="content__social_img" src="@/assets/img/4.svg" alt="icon" target="_blank">
              </a>
              <a href="" class="content__social_item">
                <img class="content__social_img" src="@/assets/img/2.svg" alt="icon" target="_blank">
              </a>
            </div>
            <p class="content__social_text">Privacy Policy</p>
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
.footer {
    position: relative;
    padding: 120px 70px 132px;
    width: 100%;
    height: 570px;
    background-color: #17191D;
    color: #fff;
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
        @media (max-width: 768px) {
          margin-bottom: 30px;
          font-size: 24px;
          line-height: 28px;
        }
    }
    &__g {
      position: absolute;
      top: 10%;
      right: 70px;
      width: 156px;
      height: 80%;
      background-image: url('@/assets/img/footer_g.png');
      background-repeat: no-repeat;
      background-size:auto;
      background-position: center;
        @media (max-width: 768px) {
          display: none;
        }
    }
    &__content {
      width: 80%;
      display: flex;
      justify-content: space-between;
        @media (max-width: 768px) {
          flex-direction: column;
          gap: 30px;
        }
    }
}
.content {
  &__title {
  font-weight: 700;
  font-size: 30px;
  line-height: 34px;
  width: max-content;
    @media (max-width: 768px) {
      font-size: 20px;
      line-height: 23px;
    }
  }
  &__box {
    display: flex;
    flex-direction: column;
  }
  &__info {
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 18px;
    text-decoration: none;
      @media (max-width: 768px) {
        gap: 12px;
        margin-bottom: 12px;
      }
    &_img {
      width: 24px;
      height: 24px;
        @media (max-width: 768px) {
          width: 16px;
          height: 16px;
        }
    }
    &_p {
      color: #fff;
    }
  }
  &__social {
    display: flex;
    gap: 20px;
      @media (max-width: 768px) {
        gap: 16px;
      }
    &_img {
      width: 34px;
      height: 34px;
        @media (max-width: 768px) {
          width: 24px;
          height: 24px;
        }
    }
    &_text {
      font-weight: 400;
      font-size: 18px;
      line-height: 21px;
      color: #B1B1B1;
      margin-top: 34px;
        @media (max-width: 768px) {
          margin-top: 24px;
          font-size: 16px;
          line-height: 18px;
        }
    }
  }
}
hr {
  width: 130px;
  height: 2px;
  border: none;
  background: #FF0B53;
  margin-bottom: 32px;
    @media (max-width: 768px) {
      width: 90px;
      margin-bottom: 20px;
    }
}
</style>
