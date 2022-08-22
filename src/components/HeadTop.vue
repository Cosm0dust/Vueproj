<template>
  <header class="header">
    <div class="header__text">
      <h1>Top reapers</h1>
      <h2>
        Curious about the journey? Perhaps your time will come soon for advancement? You would require your own
        unique soul for ascension</h2>
    </div>
    <div class="header__img-wrapper">
      <img src="./../assets/2.png" alt="">
    </div>

  </header>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.header{
  padding: 0 0 0 7%;
  display: grid;
  grid-template:  1fr/ minmax(auto, 300px) 1fr;
  width: 100%;
  &__text{
    padding-top: 3%;
    display: flex;
    flex-direction: column;
    height: 30vh;
    justify-content: center;
    gap: 1em;
  }

  & h1{
    color: #FFFFFF;
    font-style: normal;
    font-weight: 700;
    font-size: calc(36px + 18 * (100vw / 1920));
  }

  & h2{
    color: #888888;
    font-weight: 400;
    font-size: 14px;
    padding-bottom: 2em;
  }
  &__img-wrapper{
    position: relative;
    width: 100%;
  }

  &__img-wrapper img{
    position: absolute;
    top:0;
    left: 0;
    max-width: 100%;
    width: 100%;
    height: 100%;
    object-fit: none;
    object-position: top;
  }

}

</style>