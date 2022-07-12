<template>
  <div class="contacts" id="contacts">

    <div class="box contacts__box">
      <h1 class="contacts__title">Contact Us</h1>
      <form
        class="form"
        ref="contactForm"
        @submit.prevent="submitForm"
      >
        <div class="form__fb">
          <input 
            type="text" 
            class="form__input" 
            placeholder="Your Name"
            v-model.trim="form.name"
            @blur="v$.form.name.$touch"
            :class="{ error: v$.form.name.$error }"
          >
          <input 
            type="text" 
            class="form__input" 
            placeholder="Email Address"
            v-model.trim="form.email"
            @blur="v$.form.email.$touch"
            :class="{ error: v$.form.email.$error }"
          >
        </div>
        <div class="form__sb">
          <input 
            type="text" 
            class="form__input" 
            placeholder="Phone Number"
            v-model.trim="form.phone"
            @blur="v$.form.phone.$touch"
            :class="{ error: v$.form.phone.$error }"
          >
          <div class="custom-select" :tabindex="tabindex" @blur="open = false">
            <div class="selected" :class="{ open: open }" @click="open = !open">
              {{ form.job }}
            </div>
            <div class="items" :class="{ selectHide: !open }">
              <div
                v-for="(option, i) of options"
                :key="i"
                @click="
                  form.job = option;
                  open = false;
                "
              >
                {{ option }}
              </div>
            </div>
          </div>

        </div>
        <textarea 
          class="form__ta" 
          placeholder="Messege"
          v-model.trim="form.messege"
          @blur="v$.form.messege.$touch"
          :class="{ error: v$.form.messege.$error }"
        >
        </textarea>
        <div class="form__tb">
          <input 
            type="file" 
            class="form__file_i"
            id="file_i"
            @change="onFileChange"
          >
          <label 
            for="file_i"
            class="form__file"
          >
            <img
              class="form__file_img"
              src="@/assets/img/input_file.svg" 
              alt="icon"
            >
            <p class="form__file_p">Upload your CV</p>
          </label>
          <button 
            class="form__btn"
            type="submit"
          >
            Submit
          </button>
        </div>
      </form>
    </div>
        <div class="contacts__g1"></div>
    <div class="contacts__g2"></div>
  </div>
</template>

<script>
import useVuelidate from '@vuelidate/core'
import { required, email, numeric } from '@vuelidate/validators'
export default {
  setup () {
    return { v$: useVuelidate() }
  },
  data() {
    return {
      options: ['Create', 'Fix', 'Search', 'Verification'],
      default: 'Choose your job type',
      tabindex: 0,
      selected: 'Choose your job type',
      open: false,
      form: {
        name: '',
        email: '',
        phone: '',
        job: 'Choose your job type',
        messege: '',
        cv: null,
      }
    }
  },
  validations() {
    return{
      form: {
        name: { required },
        email: { required, email },
        phone: { required, numeric },
        job: { required },
        messege: { required },
      }
    }
  },
  methods: {
    async submitForm () {
      const isFormCorrect = await this.v$.$validate()
      if(isFormCorrect) {
        alert('Thanks for you messege!');
        console.log(this.form);
        this.$refs.contactForm.reset();
        this.form.job = 'Choose your job type';
      } else {
        return
      }
    },
    onFileChange(e) {
      let files = e.target.files || e.dataTransfer.files;
      if (!files.length)
        return;
      this.createFile(files[0]);
    },
    createFile(file) {
      var reader = new FileReader();
      var vm = this;
      reader.onload = (e) => {
        vm.form.cv = e.target.result;
      };
      reader.readAsDataURL(file);
    }
  }
}
</script>

<style lang="scss">
  .contacts {
    position: relative;
    padding: 120px 50px 284px;
    width: 100%;
    background-color: #F8F8F8;
      @media (max-width: 1024px) {
        padding: 50px 0;
      }
    &__box  {
      position: relative;
      z-index: 5;
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
        @media (max-width: 1024px) {
          display: none;
        }
    }
    &__g2 {
      position: absolute;
      z-index: 4;
      top: 0;
      right: 0;
      width: 100%;
      height: 100%;
      background-image: url('@/assets/img/c-g2.png');
      background-repeat: no-repeat;
      background-size: contain;
      background-position: right;
        @media (max-width: 1024px) {
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
        @media (max-width: 1022px) {
          flex-direction: column;
          gap: 15px;
        }
    }
    &__sb {
      display: flex;
      gap: 20px;
        @media (max-width: 1022px) {
          flex-direction: column;
          gap: 15px;
        }
    }
    &__tb {
      margin-top: 10px;
      display: flex;
      justify-content: space-between;
      gap: 20px;
        @media (max-width: 1022px) {      
          margin-top: 8px;
          flex-direction: column;
          align-items: center;
          gap: 15px;
        }
        @media (max-width: 768px) {      
          gap: 0;
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
        @media (max-width: 360px) {
          width: 260px;
        }
    }
    &__ta {
      font-family: 'Ubuntu', sans-serif;
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
        @media (max-width: 1022px) {
          max-width: 430px;
        }
        @media (max-width: 768px) {
          max-width: 335px;
          height: 193px;
          font-size: 16px;
          line-height: 18px;
        }
        @media (max-width: 360px) {
          width: 260px;
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
      color: #101020;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
        @media (max-width: 360px) {
          width: 260px;
        }
      &_img {
        width: 24px;
        height: 24px;
      }
      &_p {
        font-weight: 400;
        font-size: 20px;
        line-height: 23px;
        color: #101020;
      }
      &_i {
        display: none;
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
        @media (max-width: 360px) {
          width: 260px;
        }
    }
  }
  .error {
    border: 2px dashed red;
  }

  .custom-select {
    position: relative;
    width: 430px;
    height: 64px;
    text-align: left;
    outline: none;
    line-height: 64px;
    font-size: 20px;
      @media (max-width: 768px) {
        width: 335px;
        height: 50px;
        font-size: 16px;
        line-height: 50px;
      }
      @media (max-width: 360px) {
        width: 260px;
      }
  }

  .custom-select .selected {
    background-color: #fff;
    border-radius: 7px;
    box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.15);
    color: #585858;
    font-weight: 400;
    padding-left: 1em;
    cursor: pointer;
    user-select: none;
  }

  .custom-select .selected.open {
    border: 1px solid #F8F8F8;
    border-radius: 7px 7px 0px 0px;
  }

  .custom-select .selected:after {
    position: absolute;
    content: "⌵";
    top: 0;
    right: 20px;
    width: 0;
    height: 0;
  }

  .custom-select .items {
    font-weight: 300;
    color: #585858;
    border-radius: 0px 0px 6px 6px;
    overflow: hidden;
    border-right: 1px solid #F8F8F8;
    border-left: 1px solid #F8F8F8;
    border-bottom: 1px solid #F8F8F8;
    position: absolute;
    background-color: #fff;
    left: 0;
    right: 0;
    z-index: 1;
  }

  .custom-select .items div {
    color: #585858;
    padding-left: 1em;
    cursor: pointer;
    user-select: none;
  }

  .custom-select .items div:hover {
    background-color: #F8F8F8;
  }

  .selectHide {
    display: none;
  }
</style>
