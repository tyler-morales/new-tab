<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <QuoteBox />
  </div>
</template>

<script>
import QuoteBox from '@/components/QuoteBox'

export default {
  name: 'App',
  components: {
    QuoteBox
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  background: linear-gradient(
      to bottom,
      rgba(245, 246, 252, 0) 45%,
      rgb(0, 0, 0) 100%
    ),
    url('https://upload.wikimedia.org/wikipedia/commons/a/a5/Tsunami_by_hokusai_19th_century.jpg')
      no-repeat center fixed;
  background-size: cover;
  max-width: 100vw;
  height: 100vh;
  align-items: end;
  padding: 100px;

  display: grid;
}
</style>
