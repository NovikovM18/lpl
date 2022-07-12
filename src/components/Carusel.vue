<template>
  <div class="image-slider swiper-container">
    <Swiper 
      class="image-slider__wrapper swiper-wrapper"
      :space-between="20"
      :navigation="{nextEl: '.next', prevEl: '.prev'}"
      :scrollbar="{el: '.swiper-scrollbar', draggable: true}"
    >
      <SwiperSlide 
        v-for="s in activeTeam" :key="s.id"
        class="image-slider__slide swiper-slide"
      >
      <div class="image-slider__image">
        <img 
          :src="s.photo" 
          alt="photo"
          class="photo"
        >
          <div class="s-info">
            <p class="name">{{s.name}}</p>
            <p class="position">{{s.position}}</p>
            <button 
              class="btn"
              @click="openModal(s)"
            >
              Read More
            </button>
          </div>
      </div>
      </SwiperSlide>
      <div class="controls">
        <div class="swiper-scrollbar"></div>
        <div class="controls__navigation">
          <div class="nav-indicator prev"></div>
          <div class="nav-indicator next"></div>
        </div>
      </div>
    </Swiper>
  </div>
  <Modal
    v-if="showModal"
    :info="info"
    @closedModal="closeModal"
  />
</template>

<script>
import SwiperCore, {Navigation, Scrollbar,} from 'swiper';
import {Swiper, SwiperSlide} from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/bundle';
import Modal from './Modal.vue';

SwiperCore.use([Navigation, Scrollbar]);

export default {
  components: {
    Swiper,
    SwiperSlide,
    Modal
  },
  props: {
    activeTeam: {
      type: Array,
      required: true,
    }
  },
  data() {
    return {
      slides: [],
      info: {},
      showModal: false
    }
  },
  methods: {
    openModal(s) {
      this.info = s;
      this.showModal = true;
      console.log(this.info);
      document.body.classList.add('hidden');
    },
    closeModal() {
      this.showModal = false;
      document.body.classList.remove('hidden');
    }
  },
  mounted() {
  }
}
</script>

<style lang="scss">
  .swiper-container{
    width: 100%;
  }
  .swiper-wrapper {
    width: 100%;
    height: 425px;
      @media (max-width: 768px) {
        height: 300px;
      }
  }
  .swiper-slide {
    max-width: 430px;
      @media (max-width: 768px) {
        max-width: 335px;
      }
  }
  .image-slider__image {
    position: relative;
    width: 430px;
    height: 375px;  
    border: 1px solid #9A9A9A;
    border-radius: 5px;
      @media (max-width: 768px) {
        width: 335px;
        height: 268px;     
      }
  }
  .s-info {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: rgba(1, 1, 1, 0.4);
    opacity: 0;
    transition: 500ms;
  }
  .image-slider .swiper-slide {
    width: auto;
  }

  .image-slider__image:hover > .photo {
    opacity: 0.85;
    transition: 500ms;
  }
  .image-slider__image:hover > .s-info {
    opacity: 1;
    transition: 500ms;
  }

  .photo {
    z-index: -1;
    position: absolute;
    width: 100%;
    height: 100%;
    opacity: 1;
    transition: 500ms;
  }
  .name {
    font-weight: 500;
    font-size: 30px;
    line-height: 34px;
    color: #FFFFFF;
      @media (max-width: 768px) {
        font-size: 24px;
        line-height: 28px;
      }
  }
  .position {
    margin-top: 10px;
    font-weight: 400;
    font-size: 24px;
    line-height: 28px;
    color: #F2F2F2;
      @media (max-width: 768px) {
        margin-top: 6px;
        font-size: 20px;
        line-height: 23px;
      }
  }
  .btn {
    margin-top: 30px;
    width: 267px;
    height: 64px;
    background: #FF0B53;
    border-radius: 49px;
    border: none;
    color: #FFFFFF;
    font-weight: 400;
    font-size: 24px;
    line-height: 28px;
    cursor: pointer;
      @media (max-width: 768px) {
        margin-top: 20px;
        width: 233px;
        height: 56px;
        font-size: 20px;
        line-height: 23px;
      }
  }

  .controls {
    width: 100%;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    &__navigation {
      z-index: 5;
      position: absolute;
      right: 0;
      bottom: 0;
      display: flex;
      gap: 1rem;
        @media (max-width: 768px) {
          display: none;
        }
    }
  }
  .prev {
    width: 50px;
    height: 50px;
    background-image: url('../assets/img/rb.svg');
    transform: rotate(180deg);
    cursor: pointer;
  }
  .next {
    width: 50px;
    height: 50px;
    background-image: url('../assets/img/rb.svg');
    cursor: pointer;
  }
  .swiper-scrollbar {
    z-index: 5;
    max-width: 70%;
      @media (max-width: 768px) {
        max-width: 100%;
      }
  }
  .swiper-scrollbar-drag {
    height: 8px;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.15);
    border-radius: 1px;
    cursor: pointer;
    background-color: #17191D;
  }
</style>