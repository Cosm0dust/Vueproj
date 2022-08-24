<template>
  <div class="modal-window" v-if="show === true" @click.stop="hideModal">
  <div @click.stop class="pop-up" >
    <div class="pop-up__head">
      <img src=".././assets/ava.png" alt="">
      <h2 class="pop-up__head_name">SonOfLasG</h2>
      <button @click="hideModal"  class="pop-up__head_close">
        <img src=".././assets/close.png" alt="">
      </button>
    </div>


    <achieve-wrap :title="title.activityPoints"  >
      <div class="achieves__points-list"  >
        <div class="elem" :key="idx"  v-for="(gamer, idx) in modalGamer.activityPoints">
          <div class="elem_num">{{gamer.amount}}</div>
          <div>{{ gamer.media }}</div>
        </div>
      </div>
    </achieve-wrap>


    <achieve-wrap :title="title.souls"  >
      <div class="achieves__points-list"  >
        <div class="elem" :key="idx"  v-for="(soul, idx) in modalGamer.souls">
          <div>
            <svg width="37" height="38" viewBox="0 0 37 38" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M2 23.3629V14.6326C2 11.6956 3.562 8.98045 6.09933 7.50278L14.3493 2.70128C16.9142 1.20895 20.084 1.20895 22.6488 2.70128L30.8988 7.50278C33.438 8.98045 35 11.6956 35 14.6326V23.3629C35 26.2999 33.438 29.0151 30.9007 30.4928L22.6507 35.2943C20.0858 36.7866 16.916 36.7866 14.3512 35.2943L6.10117 30.4928C3.562 29.0151 2 26.2999 2 23.3629Z" :stroke="soul.color" stroke-width="2.75" stroke-linecap="round" stroke-linejoin="round"/>
              <text x="16" y="23" :fill="soul.color" class="svg-num">{{soul.amount}}</text>
            </svg>
          </div>
          <div :style="{color: soul.color}">{{soul.title}}</div>
        </div>
        </div>
    </achieve-wrap>

    <achieve-wrap :title="title.perks"  >
      <div class="achieves__points-list"  >
        <div class="elem" :key="idx"  v-for="(perk, idx) in modalGamer.perks">
            <div class="elem_doubled">
              <img :src="perk.image" alt="item">
              <img src="./../assets/double.svg" alt="*">
              <span class="elem_num">{{perk.amount}}</span>
            </div>
            <div>{{perk.title}}</div>
        </div>
      </div>
    </achieve-wrap>


    <achieve-wrap :title="title.crystals"  >
      <div class="achieves__points-list"  >
        <div class="elem" :key="idx"  v-for="(crystal, idx) in modalGamer.crystals">
          <div class="elem_doubled">
            <img :src="crystal.img" alt="item">
            <img src="./../assets/double.svg" alt="*">
            <span class="elem_num">{{crystal.amount}}</span>
          </div>
          <div>{{crystal.title}}</div>
        </div>
      </div>
    </achieve-wrap>


    <achieve-wrap :title="title.achievments"  >
      <div class="achieves__points-list" >
        <div class="elem" :key="idx"  v-for="(item, idx) in modalGamer.achievements">
          <div>
          <img class="elem__achive" :src="item.achieve" alt="">
          </div>
      </div>
      </div>
    </achieve-wrap>


  </div>
  </div>

</template>

<script>
import AchieveWrap from "@/components/AchieveWrap";

export default {
  name: "ModalWindow",
  components:{
    AchieveWrap,
  },
  props: {
    show: {
      type: Boolean,
      default: false,
    },
    modalGamer: {
      type: Object,
      requied: true,
    }


  },
  data(){
    return{
      title:{
        activityPoints:'Activity points',
        souls:'Souls',
        perks: 'Perks',
        crystals:'Crystals',
        achievments: 'Achievements',
      }
    }
  },
  methods: {
    hideModal () {
      this.$emit('update:show', false)
    }
  }
}
</script>

<style lang="scss" >
.modal-window{
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  position: fixed;
  display: flex;
}

.pop-up{
  margin: auto;
  background: #141414;
  min-width: 400px;
  width: 30%;
  min-height: 70%;

  overflow: hidden;

  box-shadow: 0px 10px 44px rgba(0, 0, 0, 0.5), inset 0px 0px 2px rgba(98, 98, 98, 0.25);
  border-radius: 20px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-bottom: 5rem;

  &__head{
     display: flex;
     align-items: center;
    position: relative;

    &_name{
      font-style: normal;
      font-weight: 700;
      font-size: 37px;
      line-height: 110%;

      color: #FFFFFF;

      padding-left: 10%;
    }

    &_close{
      position: absolute;
      top: 0;
      display: flex;
      left: 93%;
      width:2em;
      height: 2em;
      & img{
        max-width: 100%;
        max-height: 100%;
      }
    }

   }

  &__head img{
    width: 128px;
    height: 128px;
  }
}

.achieves {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;


  font-family: 'Helvetica Neue';
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 100%;

  color: #888888;

  padding: 7% 15% 0 15% ;

  &__title{
    display: grid;
    grid-template: 1fr  / 1fr auto 1fr;
    width: 100%;
    align-items: center;
    gap: 1em;

    &_front-lane{
      height: 1px;
      background:#444444;
    }
    &_back-lane{
      height: 1px;
      background: #444444;
    }
  }

  &__points-list {
    display: flex;
    width: 100%;
    flex-direction: row;
    justify-content: space-around;
  }


  & h3{
    font-family: 'Helvetica Neue';
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 100%;

    color: #E8E8E8;
  }


}

.elem{
  flex: 1 1 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;

  align-items: center;
  &_num{
    font-family: 'Helvetica Neue';
    font-style: normal;
    font-weight: 700;
    font-size: 24px;
    line-height: 100%;
    /* identical to box height, or 24px */

    text-align: center;

    /* light */

    color: #E8E8E8;
  }

  & > * {
    padding-top: 5%;
  }


  &__achive{
    mix-blend-mode: screen;
  }



}

svg{

  &-num{
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 100%;
    /* identical to box height, or 14px */

    text-align: center;
  }
}




</style>