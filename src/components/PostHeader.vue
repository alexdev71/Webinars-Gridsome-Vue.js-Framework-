<template>
  
</template>

<script>
import moment from 'moment'
import Parallax from "vue-parallaxy"

export default {
  props: ['post'],
  components: {
    Parallax
  },
  methods: {
    titleCase(str) {
      return str.replace('-', ' ')
                .split(' ')
                .map((s) => s.charAt(0).toUpperCase() + s.substring(1))
                .join(' ')
    }
  },
  computed: {
    formattedPublishDate() {
      return moment(this.post.datetime).format('DD MMMM, YYYY');
    },
    speedFactor() {
      return this.post.fullscreen ? 0.21 : 0.37
    }
  },
}
</script>
