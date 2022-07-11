<template>
  <div class="contacts" id="contacts">
    <div class="contacts__g1"></div>
    <div class="contacts__g2"></div>
    <div class="box contacts__box">
      <h1 class="contacts__title">Contact Us</h1>
      <form 
        class="form"
        @submit=""
      >
        <div class="form__fb">
          <input 
            type="text" 
            class="form__input" 
            placeholder="Your Name"
            v-model.trim="form.name"
          >
          <input 
            type="text" 
            class="form__input" 
            placeholder="Email Address"
            v-model.trim="form.email"
          >
        </div>
        <div class="form__sb">
          <input 
            type="text" 
            class="form__input" 
            placeholder="Phone Number"
            v-model.trim="form.phone"
          >
          <input 
            type="text" 
            class="form__input" 
            placeholder="Choose your job type"
            v-model="form.job"
          >
        </div>
        <textarea 
          class="form__ta" 
          placeholder="Messege"
          v-model.trim="form.messege"
        >
        </textarea>
        <div class="form__tb">
          <input type="file" class="form__file">
          <button 
            class="form__btn"
            type="submit"
          >
            Submit
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        job: '',
        messege: '',
      }
    }
  }
}
</script>

<style lang="scss">
  .contacts {
    position: relative;
    padding: 120px 50px 284px;
    width: 100%;
    height: 130vh;
    background-color: #F8F8F8;
      @media (max-width: 768px) {
        padding: 50px 0;
        height: 110vh;
      }
    &__box  {
      position: absolute;
      margin: 0 auto;
      z-index: 15;
    }
    &__title {
      margin-bottom: 90px;
      font-weight: 700;
      font-size: 54px;
      line-height: 62px;
      color: #101020;
        @media (max-width: 768px) {
          margin-bottom: 40px;
          font-size: 24px;
          line-height: 28px;
        }
    }
    &__g1 {
      position: absolute;
      bottom: 30px;
      left: 30px;
      width: 423px;
      height: 147px;
      background-image: url('@/assets/img/c_g1.png');
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
        @media (max-width: 768px) {
          display: none;
        }
    }
    &__g2 {
      position: absolute;
      top: 0;
      right: 0;
      width: 100%;
      height: 100%;
      background-image: url('@/assets/img/c-g2.png');
      background-repeat: no-repeat;
      background-size: contain;
      background-position: right;
        @media (max-width: 768px) {
          opacity: 0.5;
        }
    }
  }
  .form {
    z-index: 5;
    display: flex;
    flex-direction: column;
    gap: 20px;
      @media (max-width: 768px) {
        gap: 15px;
      }
    &__fb {
      display: flex;
      gap: 20px;
        @media (max-width: 768px) {
          flex-direction: column;
          gap: 15px;
        }
    }
    &__sb {
      display: flex;
      gap: 20px;
        @media (max-width: 768px) {
          flex-direction: column;
          gap: 15px;
        }
    }
    &__tb {
      margin-top: 10px;
      display: flex;
      justify-content: space-between;
      gap: 20px;
        @media (max-width: 768px) {      
          margin-top: 5px;
          flex-direction: column;
          align-items: center;
          gap: 15px;
        }
    }
    &__input {
      padding: 0 20px;
      width: 430px;
      height: 64px;
      background-color: #FFFFFF;
      box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.15);
      border-radius: 7px;
      font-weight: 300;
      font-size: 20px;
      line-height: 23px;
      color: #585858;
      border: none;
        @media (max-width: 768px) {
          width: 335px;
          height: 50px;
          font-size: 16px;
          line-height: 18px;
        }
    }
    &__ta {
      padding: 20px;
      max-width: 880px;
      height: 222px;
      background-color: #FFFFFF;
      box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.15);
      border-radius: 7px;
      font-size: 20px;
      line-height: 23px;
      color: #585858;
      border: none;
        @media (max-width: 768px) {
          max-width: 335px;
          height: 193px;
          font-size: 16px;
          line-height: 18px;
        }
    }
    &__file {
      width: 284px;
      height: 57px;
      border: 1px solid #101020;
      border-radius: 7px;
      font-weight: 400;
      font-size: 20px;
      line-height: 23px;
      text-align: center;
      color: #101020;
        @media (max-width: 768px) {
          width: 335px;
          height: 50px;
        }
    }
    &__btn {
      width: 284px;
      height: 64px;
      background-color: #101020;
      border-radius: 36px;
      border: none;
      font-weight: 400;
      font-size: 24px;
      line-height: 28px;
      text-align: center;
      color: #FFFFFF;
        @media (max-width: 768px) {
          margin-top: 30px;
          height: 60px;
          font-size: 20px;
          line-height: 23px;
        }
    }
  }
</style>
