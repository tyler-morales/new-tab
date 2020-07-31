<template>
  <div id="app" :style="imageStyleObject">
    <Clock />
    <QuoteBox />
  </div>
</template>

<script>
import QuoteBox from '@/components/QuoteBox'
import Clock from '@/components/Clock'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    QuoteBox,
    Clock
  },
  data() {
    return {
      image: ''
    }
  },
  methods: {
    renderImage: function() {
      axios
        .get(
          // 'https://api.unsplash.com/photos/random/?client_id=8rzeKbxcD7bHreUEfXY7wpS4VfYNHg1NTMBqucML0iw'
        )
        .then(response => {
          console.log([response.data, response.data.location.title])
          console.log('🎉 Image loaded succesfully')
          this.image = response.data.urls.regular
        })
    }
  },
  mounted: function() {
    this.renderImage()
  },
  computed: {
    // will be re-computed when the image property changes
    imageStyleObject() {
      return {
        backgroundImage: `linear-gradient(to bottom,rgba(245, 246, 252, 0) 45%,rgb(0, 0, 0) 100%), url(${this.image})`,
        backgrountRepeat: 'no-repeat',
        backgroundSize: 'cover',
        backgroundPosition: 'center'
      }
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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: white;
  background-color: black;
  max-width: 100vw;
  height: 100vh;
  align-items: end;
  padding: 75px;
  display: grid;
  grid-template-rows: repeat(12, 1fr);
}
</style>
