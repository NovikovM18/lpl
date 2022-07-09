<template>
  <div class="team" id="team">
    <div class="box team__box">
      <h1 class="partners__title">Our Team</h1>
      <div class="team__content">
        <div class="text">
          <h3 class="text__title">About</h3>
          <p class="text__p">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Fusce nullam ac sed eget. Dui in eget a tristique.</p>
        </div>

        <div class="info">
          <ul class="info__list">
            <li class="info__item" v-on:click="setActive('Team1')" :class="{ active: isActive('Team1') }">
              <img src="@/assets/img/tli_a.svg" alt="" class="info__item_c" v-if="activeItem === 'Team1'">
              <img src="@/assets/img/tli.svg" alt="" class="info__item_c" v-else>
              <p class="info__item_p">Team1</p> 
            </li>

            <li class="info__item" v-on:click="setActive('Team2')" :class="{ active: isActive('Team2') }">
              <img src="@/assets/img/tli_a.svg" alt="" class="info__item_c" v-if="activeItem === 'Team2'">
              <img src="@/assets/img/tli.svg" alt="" class="info__item_c" v-else>
              <p class="info__item_p">Team2</p> 
            </li>

            <li class="info__item" v-on:click="setActive('Team3')" :class="{ active: isActive('Team3') }">
              <img src="@/assets/img/tli_a.svg" alt="" class="info__item_c" v-if="activeItem === 'Team3'">
              <img src="@/assets/img/tli.svg" alt="" class="info__item_c" v-else>
              <p class="info__item_p">Team3</p> 
            </li>
          </ul>

          <div class="slider">

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return { 
      activeItem: 'Team1',
      activeTeam: [],
      team1: [
        {
          id: 1,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        },
        {
          id: 2,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        },
        {
          id: 3,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        },
        {
          id: 4,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        },
        {
          id: 5,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        }
      ],
      team2: [
        {
          id: 1,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        },
        {
          id: 2,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        }
      ],
      team3: [
        {
          id: 1,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        },
        {
          id: 2,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        },
        {
          id: 3,
          photo: '',
          name: 'Tom Dou',
          position: 'Front-End',
          phone: '+3125789075',
          email: 'username@mail.com',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce nullam ac sed eget. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Dui in eget a tristique. Curabitur massa nec non egestas nisl. Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
        }
      ]
    }
  },
  methods: {
    isActive: function (menuItem) {
      return this.activeItem === menuItem;
    },
    setActive: function (menuItem) {
      this.activeItem = menuItem;
      switch(menuItem) {
        case 'Team1':
          this.activeTeam = this.team1;
        break;
        case 'Team2':
          this.activeTeam = this.team2;
        break;
        case 'Team3':
          this.activeTeam = this.team3;
        break;
        default:
        break;
      }
    }
  },
  mounted() {
    this.activeItem = this.team1;
  }
}
</script>

<style lang="scss">
  .team {
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
  .text {
    max-width: 430px;
    height: auto;
    &__title {
      margin-top: 210px;
      font-weight: 500;
      font-size: 34px;
      line-height: 39px;
      color: #101020;
        @media (max-width: 768px) {
          margin-top: 30px;
        }
    }
    &__p {
      margin-top: 18px;
      font-weight: 300;
      font-size: 24px;
      line-height: 147%;
      color: #3D3D3D;
        @media (max-width: 768px) {
          margin-top: 14px;
        }
    }
  }
  .info {
    display: flex;
    flex-direction: column;
    &__list {
      width: max-content;
      display: flex;
      list-style: none;
      background-color: #F0F0F0;
      border-radius: 61px;
        @media (max-width: 768px) {
          margin-top: 40px;
        }
    }
    &__item {
      padding: 20px 40px;
      border-radius: 61px;
      display: flex;
      align-items: center;
      gap: 18px;
      cursor: pointer;
      transition: 500ms;
        @media (max-width: 768px) {
          padding: 8px 12px;
          gap: 8px;
        }
      &:hover {
        background-color: #FF0B53;
        transition: 500ms;
      }
      &_c {
        width: 24px;
        height: 24px;
          @media (max-width: 768px) {
            width: 18px;
            height: 18px;
          }
      }
      &_p {
        text-decoration: none;
        font-weight: 400;
        font-size: 24px;
        line-height: 28px;
        text-align: center;
        color: #101020;
        
          @media (max-width: 768px) {
            font-size: 18px;
            line-height: 21px;
          }
      }
    }
  }
  .active {
    color: #FFF;
    background-color: #FF0B53;
  }
  .active > p {
    color: #FFF;
  }

</style>
