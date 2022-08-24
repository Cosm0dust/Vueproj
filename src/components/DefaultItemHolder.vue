<template>
  <div class="list">
    <span>{{ item.index }}</span>
    <span>{{ item.ava }}</span>
    <span class="list__discord">{{ item.DiscordID }}</span>
    <span>{{ item.points }}</span>
    <span>{{ item.activity }}</span>
    <span>{{ item.crystals }}</span>
    <span class="list__achieve_1"> {{ item.achievements }}</span>
  </div>
</template>

<script>
export default {
  name: "DefaultItemHolder",
  props: {
    item:{
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