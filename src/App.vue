<template>
  <div class="wrapper">
    <div class="container">
      <head-top />
      <div class="content">
        <div class="options">
          <div class="selectors">
            <button @click="toggleClasst" :class="isActive.total ? 'active' : ''">Total</button>
            <button  @click="toggleClassc" :class="isActive.comunity ? 'active' : ''">Comunity</button>
            <button @click="toggleClassg" :class="isActive.game ? 'active' : ''">The Game</button>
          </div>
          <div class="time">
            <div @click="toggleClassa" :class="isActive.allTime ? 'alltime active' : 'alltime'">All time</div>
            <div @click="toggleClassl" :class="isActive.lastMonth ? 'active' : ''">Last month</div>
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
         (isActive.comunity && isActive.lastMonth) ? filteredMonthUsers :
         (isActive.game && isActive.lastMonth) ? filteredMonthGamers :
          ''">
          <span>{{ idx + 1}}</span>
          <span>{{gamer.ava}}</span>
          <span>{{ gamer.DiscordID }}</span>
          <span>{{ gamer.points }}</span>
          <span>{{ gamer.activity }}</span>
          <span>{{ gamer.crystals }}</span>
           <span v-if="gamer.achievements === 1">
           </span>
          <span v-else-if="gamer.achievements === 2"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
          </span>
          <span v-else-if="gamer.achievements === 3"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
          </span>
          <span v-else-if="gamer.achievements === 4"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
          </span>
          <span v-else-if="gamer.achievements === 5"><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" ><img src="./assets/Group.svg" alt="" >
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
          ava: 'img',
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
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
        },
        {
          ava: 'img',
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: true,
          lastMonth: false,
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
      return this.gamers.filter(gamer => (gamer.game === true) && (gamer.lastMonth === false) );
    },
  }
}

</script>

<style>
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
  background: url("./assets/2.png") right/cover no-repeat;
}


.container .content{
  background: #101010;
}

.options{
  padding: 2em 7%;
  display: flex;
  justify-content:space-between;
  width: 85%;
}

button{
  background: transparent;
}

.options .selectors{
  display: flex;
}
.selectors> *{
  font-style: normal;
  font-weight: 400;
  font-size: 17px;
  line-height: 20px;

  /* grey */

  color: #888888;

  padding-right: 3em;

}

.selectors:last-child{
  margin-right: 0;
}

.selectors .active{
  font-style: normal;
  font-weight: 400;
  font-size: 17px;
  line-height: 20px;


  color: #E8E8E8;

  text-decoration: underline;
  text-decoration-color: #C2E900;

}

.time{
  display: flex;

  color: #888888;
}

.time .active{
  color: #E8E8E8;
}

.time .alltime::after{
  margin-left: 0.5em;
  content: '/';
  color: #E8E8E8;
}

.time > * {
  padding-left: 0.5em;
  flex-shrink: 0;
}

.default-list{
  display: grid;
  width: 80%;
  padding: 0 8% 1em 8%;
  grid-template: 1fr / 1fr 1fr 4fr 1fr 1fr 1fr 2fr;
  font-weight: 400;
  font-size: 17px;
  line-height: 20px;
  gap: 1rem;
  color: #818181;


}

.list{
  color: white;
  display: grid;
  width: 80%;
  padding: 0 8% 1em 8%;
  grid-template: 1fr / 1fr 1fr 4fr 1fr 1fr 1fr 2fr;
  font-weight: 400;
  font-size: 17px;
  line-height: 20px;
  gap: 1rem;
}


</style>
