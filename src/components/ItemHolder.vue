<template>
  <div class="list__items">
  <span>{{ idx + 1}}</span>
  <span class="list__img-wrap"><img :src="gamer.ava" alt=""></span>
  <span class="list__discord">{{ gamer.DiscordID }}</span>
  <span>{{ gamer.points }}</span>
  <span>{{ gamer.activity }}</span>
  <span>{{ gamer.crystals }}</span>
  <span class="list__achieve" v-if="gamer.achievements === 1">
             <img src="@/assets/Group.svg" alt="" >
           </span>
  <span class="list__achieve" v-else-if="gamer.achievements === 2"><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" >
          </span>
  <span class="list__achieve" v-else-if="gamer.achievements === 3"><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" >
          </span>
  <span class="list__achieve" v-else-if="gamer.achievements === 4"><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" >
          </span>
  <span class="list__achieve" v-else-if="gamer.achievements === 5"><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" ><img src="@/assets/Group.svg" alt="" >
          </span>
  </div>
</template>

<script>
export default {
  name: "ItemHolder",
  props: {
    gamer:{
      type:  Object,
      requied: true,
    },
    idx:{
      type: Number,
      requied: true,
    }
  }

}
</script>

<style scoped>

</style>