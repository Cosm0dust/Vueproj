<template>
  <div class="modal-window" v-if="show === true" @click.stop="hideModal">
  <div @click.stop class="pop-up" >
    <div class="pop-up__head">
      <img src=".././assets/ava.png" alt="">
      <h2 class="pop-up__head_name">SonOfLasG</h2>
    </div>

    <div class="achieves">
      <h3>Activity points</h3>
      <div class="achieves__points-list">
        <div class="elem">
          <div class="elem_num">1524</div>
          <div>Twitter</div>
        </div>
        <div class="elem">
          <div class="elem_num">523</div>
          <div>Discord</div>
        </div>
        <div class="elem">
          <div class="elem_num">54</div>
          <div>Web</div>
        </div>
      </div>
    </div>

    <div class="achieves">
      <h3>Souls</h3>
      <div class="achieves__points-list">
        <div class="elem">
          <div >
            <svg width="37" height="38" viewBox="0 0 37 38" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M2 23.3629V14.6326C2 11.6956 3.562 8.98045 6.09933 7.50278L14.3493 2.70128C16.9142 1.20895 20.084 1.20895 22.6488 2.70128L30.8988 7.50278C33.438 8.98045 35 11.6956 35 14.6326V23.3629C35 26.2999 33.438 29.0151 30.9007 30.4928L22.6507 35.2943C20.0858 36.7866 16.916 36.7866 14.3512 35.2943L6.10117 30.4928C3.562 29.0151 2 26.2999 2 23.3629Z" stroke="#E8E8E8" stroke-width="2.75" stroke-linecap="round" stroke-linejoin="round"/>
              <text x="16" y="23" fill="#E8E8E8" class="svg-num">3</text>
            </svg>
          </div>
          <div :style="{color: '#FFFFFF'}">Total</div>
        </div>
        <div class="elem">
          <div >
            <svg width="37" height="38" viewBox="0 0 37 38" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M2 23.3629V14.6326C2 11.6956 3.562 8.98045 6.09933 7.50278L14.3493 2.70128C16.9142 1.20895 20.084 1.20895 22.6488 2.70128L30.8988 7.50278C33.438 8.98045 35 11.6956 35 14.6326V23.3629C35 26.2999 33.438 29.0151 30.9007 30.4928L22.6507 35.2943C20.0858 36.7866 16.916 36.7866 14.3512 35.2943L6.10117 30.4928C3.562 29.0151 2 26.2999 2 23.3629Z" stroke="#C2E900" stroke-width="2.75" stroke-linecap="round" stroke-linejoin="round"/>
              <text x="16" y="23" fill="#C2E900" class="svg-num">3</text>
            </svg>
          </div>
          <div :style="{color: '#C2E900'}">Personal</div>
        </div>
        <div class="elem">
          <div >
            <svg width="37" height="38" viewBox="0 0 37 38" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M2 23.3629V14.6326C2 11.6956 3.562 8.98045 6.09933 7.50278L14.3493 2.70128C16.9142 1.20895 20.084 1.20895 22.6488 2.70128L30.8988 7.50278C33.438 8.98045 35 11.6956 35 14.6326V23.3629C35 26.2999 33.438 29.0151 30.9007 30.4928L22.6507 35.2943C20.0858 36.7866 16.916 36.7866 14.3512 35.2943L6.10117 30.4928C3.562 29.0151 2 26.2999 2 23.3629Z" stroke="#E8E8E8" stroke-width="2.75" stroke-linecap="round" stroke-linejoin="round"/>
              <text x="16" y="23" fill="#E8E8E8" class="svg-num">1</text>
            </svg>
          </div>
          <div :style="{color: '#FFFFFF'}">Relocated</div>
        </div>
        <div class="elem">
          <div >
            <svg width="37" height="38" viewBox="0 0 37 38" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M2 23.3629V14.6326C2 11.6956 3.562 8.98045 6.09933 7.50278L14.3493 2.70128C16.9142 1.20895 20.084 1.20895 22.6488 2.70128L30.8988 7.50278C33.438 8.98045 35 11.6956 35 14.6326V23.3629C35 26.2999 33.438 29.0151 30.9007 30.4928L22.6507 35.2943C20.0858 36.7866 16.916 36.7866 14.3512 35.2943L6.10117 30.4928C3.562 29.0151 2 26.2999 2 23.3629Z" stroke="#888888" stroke-width="2.75" stroke-linecap="round" stroke-linejoin="round"/>
              <text x="16" y="23" fill="#888888" class="svg-num">0</text>
            </svg>
          </div>
          <div :style="{color: '#888888'}">Merged</div>
        </div>
        <div class="elem">
          <div >
            <svg width="37" height="38" viewBox="0 0 37 38" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M2 23.3629V14.6326C2 11.6956 3.562 8.98045 6.09933 7.50278L14.3493 2.70128C16.9142 1.20895 20.084 1.20895 22.6488 2.70128L30.8988 7.50278C33.438 8.98045 35 11.6956 35 14.6326V23.3629C35 26.2999 33.438 29.0151 30.9007 30.4928L22.6507 35.2943C20.0858 36.7866 16.916 36.7866 14.3512 35.2943L6.10117 30.4928C3.562 29.0151 2 26.2999 2 23.3629Z" stroke="#888888" stroke-width="2.75" stroke-linecap="round" stroke-linejoin="round"/>
              <text x="16" y="23" fill="#888888" class="svg-num">0</text>
            </svg>
          </div>
          <div :style="{color: '#888888'}">Linked</div>
        </div>
      </div>
    </div>

    <div class="achieves">
      <h3>Perks</h3>
      <div class="achieves__points-list">
        <div class="elem">
          <div class="elem_doubled">
            <img src="./../assets/relocation.svg" alt="item">
            <img src="./../assets/double.svg" alt="*">
            <span class="elem_num">15</span>
          </div>
          <div>Relocation</div>
        </div>
        <div class="elem">
          <div class="elem_doubled">
            <img src="./../assets/merging.svg" alt="item">
            <img src="./../assets/double.svg" alt="*">
            <span class="elem_num">5</span>
          </div>
          <div>Merging</div>
        </div>
        <div class="elem">
          <div class="elem_doubled">
            <img src="./../assets/linking.svg" alt="item">
            <img src="./../assets/double.svg" alt="*">
            <span class="elem_num">5</span>
          </div>
          <div>Linking</div>
        </div>
      </div>
    </div>

    <div class="achieves">
      <h3>Crystals</h3>
      <div class="achieves__points-list">
        <div class="elem">
          <div class="elem_doubled">
            <img src="./../assets/img132.png" alt="item">
            <img src="./../assets/double.svg" alt="*">
            <span class="elem_num">17</span>
          </div>
          <div>Terra</div>
        </div>
        <div class="elem">
          <div class="elem_doubled">
            <img src="./../assets/Group3.png" alt="item">
            <img src="./../assets/double.svg" alt="*">
            <span class="elem_num">18</span>
          </div>
          <div>Atmos</div>
        </div>
        <div class="elem">
          <div class="elem_doubled">
            <img src="./../assets/Group4.png" alt="item">
            <img src="./../assets/double.svg" alt="*">
            <span class="elem_num">4</span>
          </div>
          <div>Aqua</div>
        </div>
      </div>
    </div>

    <div class="achieves">
      <h3>Achievements</h3>
      <div class="achieves__points-list">
        <div class="elem">
          <img class="elem__achive" src="./../assets/image4.png" alt="">
        </div>
        <div class="elem">
          <img class="elem__achive" src="./../assets/image5.png" alt="">
        </div>
        <div class="elem">
          <img class="elem__achive" src="./../assets/image8.png" alt="">
        </div>
        <div class="elem">
          <img class="elem__achive" src="./../assets/image7.png" alt="">
        </div>
      </div>
    </div>
  </div>
  </div>

</template>

<script>
export default {
  name: "ModalWindow",
  props: {
    show: {
      type: Boolean,
      default: false,
    }
  },
  data(){
    return{

    }
  },
  methods: {
    hideModal () {
      this.$emit('update:show', false)
    }
  }
}
</script>

<style lang="scss" scoped>
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

    &_name{
      font-style: normal;
      font-weight: 700;
      font-size: 37px;
      line-height: 110%;

      color: #FFFFFF;

      padding-left: 10%;
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

  &__points-list {
    display: flex;
    width: 100%;
    justify-content: space-around;
    & > *{
      flex: 1 1 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
    }
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
  display: flex;
  flex-direction: column;
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