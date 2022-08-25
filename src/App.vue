<template>
  <div class="wrapper">
    <div class="container">
      <head-top  />
      <div class="container__content">
        <div class="options">
          <div class="options__selectors" >
            <button @click="toggleClasst" :class="isActive.total ? 'options__selectors_active' : ''">Total</button>
            <button @click="toggleClassc" :class="isActive.comunity ? 'options__selectors_active' : ''">Comunity</button>
            <button @click="toggleClassg" :class="isActive.game ? 'options__selectors_active' : ''">The Game</button>
          </div>
          <div class="options__time">
            <div @click="toggleClassa" :class="isActive.allTime ? 'options__time_alltime options__time_active' : 'options__time_alltime'">All time</div>
            <div @click="toggleClassl" :class="isActive.lastMonth ? 'options__time_active' : ''">Last month</div>
          </div>
        </div>
        <div  v-bind:key="idx" v-for="(item, idx) in gamersTitle"  >
          <default-item-holder :item="item" :idx="idx"/>
        </div>

        <div  @click="showModal" v-bind:key="idx" v-for="(gamer, idx) in
        (isActive.total && isActive.allTime) ? gamers :
         (isActive.comunity && isActive.allTime)?  filteredUsers:
         (isActive.game && isActive.allTime) ? filteredGamers :
         (isActive.total && isActive.lastMonth) ? filteredTotal :
         (isActive.comunity && isActive.lastMonth) ? filteredMonthUsers :
         (isActive.game && isActive.lastMonth) ? filteredMonthGamers :
          'Error'">
          <item-holder :gamer="gamer" :idx="idx" />
        </div>
      </div>
    </div>

    <modal-window :modalGamer="gamers[0].modalWindow" v-model:show="modalVisible"  />

  </div>
</template>

<script>
import HeadTop from "@/components/HeadTop";
import ModalWindow from "@/components/ModalWindow";
import ItemHolder from "@/components/ItemHolder";
import DefaultItemHolder from "@/components/DefaultItemHolder";

export default {
  name: 'App',
  components: {
    HeadTop, ModalWindow, ItemHolder, DefaultItemHolder,
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
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
                  {
                    achieve: require('@/assets/image4.png'),
                  },
                  {
                    achieve: require('@/assets/image5.png'),
                  },
                  {
                    achieve: require('@/assets/image8.png'),
                  },
                  {
                    achieve: require('@/assets/image7.png'),
                  },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 3,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
        },
        {
          id: Math.random ().toString (36).substr (2, 9),
          ava: require('@/assets/image31.png'),
          DiscordID: 'Crypto Coin Ninja',
          points: '3.2k',
          activity: 672,
          crystals: 17,
          achievements: 1,
          comunity: true,
          game: false,
          lastMonth: true,
          modalWindow:{
            activityPoints:[
              {
                media: 'Twitter',
                amount: 1524,
              },
              {
                media: 'Discord',
                amount: 532,
              },
              {
                media: 'Web',
                amount: 24,
              }
            ],

            souls:[
              {
                title: 'Total',
                amount: 3,
                color: '#FFFFFF',
              },
              {
                title: 'Personal',
                amount: 3,
                color: '#C2E900',
              },
              {
                title: 'Relocated',
                amount: 1,
                color: '#FFFFFF',
              },
              {
                title: 'Merged',
                amount: 0,
                color: '#888888',
              },
              {
                title: 'Linked',
                amount: 0,
                color: '#888888'
              },

            ],
            perks: [
              {
                title: 'Relocation',
                amount: 15,
                image: require('@/assets/relocation.svg'),
              },
              {
                title: 'Merging',
                amount: 5,
                image: require('@/assets/merging.svg'),
              },
              {
                title: 'Linking',
                amount: 5,
                image: require('@/assets/linking.svg'),
              },

            ],
            crystals: [
              {
                title: 'Terra',
                amount: 15,
                img: require('@/assets/img132.png'),
              },
              {
                title: 'Atmos',
                amount: 18,
                img: require('@/assets/Group3.png'),
              },
              {
                title: 'Aqua',
                amount: 4,
                img: require('@/assets/Group4.png'),
              },

            ],
            achievements:[
              {
                achieve: require('@/assets/image4.png'),
              },
              {
                achieve: require('@/assets/image5.png'),
              },
              {
                achieve: require('@/assets/image8.png'),
              },
              {
                achieve: require('@/assets/image7.png'),
              },
            ],
          }
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
  height: 100vh;
  width: 100vw;
  line-height: 1;
  font-size: 14px;
  -ms-text-size-adjust: 100%;
  -moz-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  background: black;
  overflow-x: hidden;

}


.container{
  width: 100%;
  margin: 0px auto;
  overflow: hidden;
  min-height: 100vh;
  display: grid;
  grid-template: 15em 1fr/ 1fr;
  
  @media (max-width: 992px) {
    grid-template: 11em 1fr/ 1fr;
  }

  @media (max-width: 992px) {
    grid-template: 10em 1fr/ 1fr;
  }




  &__content{
    background: #101010;
    padding-bottom: 3em;
  }
}




.options{
  padding: 2em 7%;
  display: flex;
  justify-content:space-between;
  width: 100%;


  @media (max-width: 767px) {
    padding: 2em 3%;
  }

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
      font-size:  calc(12px + 5 * (100vw / 1920));
      line-height: 20px;



      color: #E8E8E8;

      text-decoration: underline;
      text-decoration-color: #C2E900;
    }
  }
  &__time{
    display: flex;
    align-self: center;
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


.list{
  color: #818181;
  display: grid;
  align-items: center;
  width: 100%;
  padding: 1em 7% 1em 7%;
  grid-template: 1fr/ minmax( 32px ,1fr)  minmax( 24px ,1fr) minmax( 133px, 4fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( auto ,2fr);
  font-weight: 400;
  font-size: calc(8px + 9 * (100vw / 1920));
  line-height: 20px;
  gap: 1rem;
  cursor: default;
  align-content: center;
  justify-items: center;
  @media (max-width: 767px) {
    align-content: center;
    justify-items: center;
    grid-template: 1fr / minmax( 24px ,1fr)  minmax( 35px ,1fr) minmax( 70px, 4fr) minmax( auto ,1fr) minmax( auto ,1fr) minmax( auto ,1fr) minmax( auto ,2fr);
    padding: 1em 3% 1em 3%;
    gap: 2px;

  }

  &__items{
    font-size: calc(12px + 5 * (100vw / 1920));
    display: grid;
    justify-items: center;
    align-content: center;
    align-items: center;
    width: 100%;
    padding: 1em 7% 1em 7%;
    grid-template: 1fr/ minmax( 32px ,1fr)  minmax( 35px ,1fr) minmax( 133px, 4fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( 32px ,1fr) minmax( auto ,2fr);
    color: white;
    font-weight: 400;
    position: relative;
    gap: 1rem;
    justify-content: center;
    cursor: pointer;

    @media (max-width: 767px) {
      padding: 1em 3% 1em 3%;
      grid-template: 1fr / minmax( 24px ,1fr)  minmax( 24px, 1fr) minmax( 70px, 4fr) minmax( auto, 1fr) minmax( auto, 1fr) minmax( auto, 1fr) minmax( auto, 2fr);
      gap: 0.5rem
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
      @media (max-width: 767px) {
      left: 3%;
        width: 94%;
      }
    }



  }

  &__discord{
    align-self: center;
    justify-self: start;
  }
  &__img-wrap{
    display: block;
    height: 48px;
    @media (max-width: 767px) {
      height: 24px;
    }
    & img{
      max-width: 100%;
      max-height: 100%;
    }
  }
  &__achieve{
    height: 20px;
    justify-self: start;
    @media (max-width: 767px) {
      height: 13px;
    }
    &_1{
      justify-self: start;

    }
    & img{
      max-width: 100%;
      max-height: 100%;
    }
  }
}



</style>
