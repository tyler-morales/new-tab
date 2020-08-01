<template>
  <blockquote class="quote-box">
    <p class="quote-box--quote">"{{ info.content }}"</p>
    <footer class="quote-box--author">
      <a :href="authorLink" target="_blank" rel="noopener noreferrer">
        – {{ info.author }}
      </a>
    </footer>
  </blockquote>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      info: '',
      loading: true,
      errored: false
    }
  },
  methods: {
    getRandomQuote: function() {
      axios
        .get('https://api.quotable.io/random')
        .then(response => {
          this.info = response.data
          console.log('🎉 Quote loaded succesfully')
        })
        .catch(error => {
          console.log(error)
          this.errored = true
        })
        .finally(() => (this.loading = false))
    }
  },
  mounted: function() {
    this.getRandomQuote()
  },
  computed: {
    authorLink: function() {
      return `https://en.wikipedia.org/wiki/${this.info.author}`
    }
  }
}
</script>

<style lang="scss" scoped>
.quote-box {
  display: grid;
  gap: 20px;
  max-width: 30vw;
  color: white;
  grid-row: -1;

  &--quote {
    font-size: 20px;
    font-style: italic;
  }
}
</style>
