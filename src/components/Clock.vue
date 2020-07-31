<template>
  <h1>{{ time }}</h1>
</template>

<script>
import moment from 'moment'

export default {
  data() {
    return {
      time: ''
    }
  },
  methods: {
    renderTime: function() {
      this.time = moment().format('MMMM Do YYYY, h:mm:ss a')
    }
  },
  mounted: function() {
    setInterval(this.renderTime, 1000)
  }
}
</script>

<style lang="scss" scoped>
h1 {
  margin-bottom: 50px;
}
</style>
