<template>
  <div class="wrapper">
    <div class="container">
      <head-top  />
      <div class="container__content">
        <div class="options">
          <div class="options__selectors">
            <button @click="toggleClasst" :class="isActive.total ? 'options__selectors_active' : ''">Total</button>
            <button @click="toggleClassc" :class="isActive.comunity ? 'options__selectors_active' : ''">Comunity</button>
            <button @click="toggleClassg" :class="isActive.game ? 'options__selectors_active' : ''">The Game</button>
          </div>
          <div class="options__time">
            <div @click="toggleClassa" :class="isActive.allTime ? 'options__time_alltime options__time_active' : 'options__time_alltime'">All time</div>
            <div @click="toggleClassl" :class="isActive.lastMonth ? 'options__time_active' : ''">Last month</div>
          </div>
        </div>
        <div  v-bind:key="idx" v-for="(item, idx) in gamersTitle" class="default-list" >
          <span>{{item.index}}</span>
          <span>{{item.ava}}</span>
          <span>{{item.DiscordID}}</span>
          <span>{{item.points}}</span>
          <span>{{item.activity}}</span>
          <span>{{item.crystals}}</span>
          <span> {{item.achievements}}</span>
        </div>
        <div  @click="showModal" class="list" v-bind:key="idx" v-for="(gamer, idx) in
        (isActive.total && isActive.allTime) ? gamers :
         (isActive.comunity && isActive.allTime)?  filteredUsers:
         (isActive.game && isActive.allTime) ? filteredGamers :
         (isActive.total && isActive.lastMonth) ? filteredTotal :
         (isActive.comunity && isActive.lastMonth) ? filteredMonthUsers :
         (isActive.game && isActive.lastMonth) ? filteredMonthGamers :
          ''">
          <span>{{ idx + 1}}</span>
          <span class="list__img-wrap"><img :src="gamer.ava" alt=""></span>
          <span>{{ gamer.DiscordID }}</span>
          <span>{{ gamer.points }}</span>
          <span>{{ gamer.activity }}</span>
          <span>{{ gamer.crystals }}</span>
           <span class="list__achive" v-if="gamer.achievements === 1">
             <img src="./assets/Group.svg" alt="" >
           </span>
          <span class="list__achive" v-else-if="gamer.achievements === 2"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
          </span>
          <span class="list__achive" v-else-if="gamer.achievements === 3"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
          </span>
          <span class="list__achive" v-else-if="gamer.achievements === 4"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
          </span>
          <span class="list__achive" v-else-if="gamer.achievements === 5"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
          </span>
        </div>
      </div>
    </div>
    <modal-window v-model:show="modalVisible"  />
  </div>
</template>

<script>
import HeadTop from "@/components/HeadTop";
import ModalWindow from "@/components/ModalWindow";

export default {
  name: 'App',
  components: {
    HeadTop, ModalWindow
  },
  data(){
    return{
      sortParam: '',

      isActive: {
        total: true,
        comunity: false,
        game: false,
        allTime: true,
        lastMonth: false,
      },
      gamersTitle:[
      {
        index:'#',
        ava: 'Ava',
        DiscordID: 'DiscordID',
        points: 'Points',
        activity: 'Activity',
        crystals: 'Crystals',
        achievements: 'Achievements',
      }
    ],
      gamers: [
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: true,
          game: false,
          lastMonth: true,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: false,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: false,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: false,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: false,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: false,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: false,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: true,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: false,
          game: true,
          lastMonth: false,
        },
        {
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 5,
          comunity: true,
          game: false,
          lastMonth: true,
        },

      ],
      modalVisible: false,
      }
    },
  methods: {

    showModal(){
      this.modalVisible = true;
    },

    toggleClasst(){
      this.isActive.total = true;
      this.isActive.comunity = false;
      this.isActive.game = false;
    },

    toggleClassc(){
      this.isActive.total = false;
      this.isActive.comunity = true;
      this.isActive.game = false;
    },

    toggleClassg(){
      this.isActive.total = false;
      this.isActive.comunity = false;
      this.isActive.game = true;
    },
    toggleClassa(){
      this.isActive.allTime = true;
      this.isActive.lastMonth = false;
    },
    toggleClassl(){
      this.isActive.allTime = false;
      this.isActive.lastMonth = true;
    }

  },
  computed:{
    filteredUsers(){
      return this.gamers.filter(gamer => gamer.comunity === true);
    },

    filteredGamers(){
      return this.gamers.filter(gamer => gamer.game === true);
    },
    filteredMonthUsers(){
      return this.gamers.filter(gamer => (gamer.comunity === true && (gamer.lastMonth === true) ));
    },
    filteredMonthGamers(){
      return this.gamers.filter(gamer => (gamer.game === true) && (gamer.lastMonth === true) );
    },
    filteredTotal(){
      return this.gamers.filter(gamer => (gamer.lastMonth === true) );
    }
  }
}

</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  border: 0;
}

*, *:before, *:after {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

:focus, :active {
  outline: none;
}

a:focus, a:active {
  outline: none;
}

nav, footer, header, aside {
  display: block;
}

input, button, textarea {
  font-family: inherit;
}

input::-ms-clear {
  display: none;
}

button {
  cursor: pointer;
}

button::-moz-focus-inner {
  padding: 0;
  border: 0;
}

a, a:visited {
  text-decoration: none;
}

a:hover {
  text-decoration: none;
}

ul li {
  list-style: none;
}

img {
  vertical-align: top;
}

button{
  background: transparent;
}

.wrapper{
  height: 100%;
  width: 100%;
  line-height: 1;
  font-size: 14px;
  -ms-text-size-adjust: 100%;
  -moz-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  background: black;
}


.container{
  max-width: 1920px;
  margin: 0px auto;
  overflow: hidden;

  display: grid;
  grid-template: minmax(165px, auto) minmax(70vh, 1fr)/ 1fr;
  background: black;

  /*background: url("./assets/2.png") right/cover no-repeat;*/

  @media (max-width:767px){
    max-width: 766px;
  }

  &__content{
    background: #101010;
  }
}




.options{
  padding: 2em 7%;
  display: flex;
  justify-content:space-between;
  width: 100%;

  &__selectors {
    display: flex;

    & > * {
    font-style: normal;
    font-weight: 400;
    font-size: calc(12px + 5 * (100vw / 1920));
    line-height: 14px;
    color: #888888;
    padding-right: 3em;
  }
    &_active{
      font-style: normal;
      font-weight: 400;
      font-size: 17px;
      line-height: 20px;


      color: #E8E8E8;

      text-decoration: underline;
      text-decoration-color: #C2E900;
    }
  }
  &__time{
    display: flex;

    color: #888888;
    &_active{
      color: #E8E8E8;
    }
    &_alltime::after{
      margin-left: 0.5em;
      content: '/';
      color: #E8E8E8;
    }
    & > * {
      padding-left: 0.5em;
      cursor: pointer;
    }
  }
}

.default-list{
  display: grid;
  width: 100%;
  padding: 0 7% 1em 7%;
  grid-template: 1fr / minmax( 32px ,1fr)  minmax( 24px ,1fr) minmax( 133px, 4fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( auto ,2fr);
  font-weight: 400;
  font-size: calc(8px + 9 * (100vw / 1920));
  line-height: 20px;
  gap: 1rem;
  color: #818181;

  @media (max-width: 767px) {
    grid-template: 1fr / minmax( auto ,1fr)  minmax( auto ,1fr) minmax( auto, 4fr) minmax( auto ,1fr) minmax( auto ,1fr) minmax( auto ,1fr) minmax( auto ,2fr);

  }
}

.list{
  color: white;
  display: grid;
  align-items: center;
  width: 100%;
  padding: 1em 7% 1em 7%;
  grid-template: 1fr/ minmax( 32px ,1fr)  minmax( 24px ,1fr) minmax( 133px, 4fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( auto ,2fr);
  font-weight: 400;
  font-size: calc(12px + 5 * (100vw / 1920));
  line-height: 20px;
  gap: 1rem;
  position: relative;

  @media (max-width: 767px) {
    grid-template: 1fr / minmax( auto ,1fr)  minmax( auto ,1fr) minmax( auto, 4fr) minmax( auto ,1fr) minmax( auto ,1fr) minmax( auto ,1fr) minmax( auto ,2fr);
  }

  &::after {
    position: absolute;
    content: '';
    width: 84%;
    left: 7%;
    bottom: 0;
    height: 1px;
    background: #333333;
    display: block;
  }
  & > * {
    cursor: pointer;
  }

}



</style>
