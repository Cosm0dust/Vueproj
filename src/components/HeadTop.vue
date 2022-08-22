<template>
  <header>


    <div class="text">
      <h1>Top reapers</h1>
      <h2>
        Curious about the journey? Perhaps your time will come soon for advancement? You would require your own
        unique soul for ascension</h2>
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style scoped>
header{
  padding: 0 7%;
  display: grid;
  grid-template:  1fr/ minmax(auto, 300px) 1fr;
}

.text{
  padding-top: 3%;
  display: flex;
  flex-direction: column;
  height: 30vh;
  justify-content: center;
  gap: 1em;
}

h1{
  color: #FFFFFF;
  font-style: normal;
  font-weight: 700;
  font-size: calc(36px + 18 * (100vw / 1920));
}

h2{
  color: #888888;
  font-weight: 400;
  font-size: 14px;
  padding-bottom: 7%;
}
</style>