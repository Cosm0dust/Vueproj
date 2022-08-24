<template>
  <div class="achieves">
    <div class="achieves__title">
      <span class="achieves__title_front-lane"></span>
      <h3 >{{ title }}</h3>
      <span class="achieves__title_back-lane"></span>
    </div>
   <slot></slot>
  </div>
</template>

<script>
export default {
  name: "AchiveWrap",
  props:{
    title:{
      type: Object,
      requied: true,
    }
  }
}
</script>

<style scoped>

</style>