<template>
  <div id="app">
    <Clock />
    <QuoteBox />
  </div>
</template>

<script>
import QuoteBox from '@/components/QuoteBox'
import Clock from '@/components/Clock'

export default {
  name: 'App',
  components: {
    QuoteBox,
    Clock
  },
  data() {
    return {
      info: '',
      loading: true,
      errored: false
    }
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
  color: white;
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
  padding: 75px;
  display: grid;
}
</style>

https://api.artic.edu/api/v1/artworks/238800
https://api.artic.edu/image-service/abcd1234/full/max/0/default.jpg
