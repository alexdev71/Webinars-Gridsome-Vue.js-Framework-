<template>
  <article>
    <div class="article_main font-sans flex mx-auto max-w-6xl my-8 bg-black" style="border-radius:15px;">
      <g-image :src="imagePath" class="software_images" style="border-top-left-radius:3%; border-bottom-left-radius:3%;" />
      <div class="ml-8 py-4">
        <header class="mb-8">
          <h2 class="text-2xl sm:text-3xl leading-tight font-sans mb-1 sm:mb-2">
            <g-link :to="`${post.path}/`" class="text-white">{{ post.title }}</g-link>
            <h2 style="width: 75px;float: right;margin-right: 40px;color:white;font-size: 38px;">$1292</h2>
          </h2><br/>
          <time class="text-white text-lg mb-2 uppercase font-medium">Date: {{ formatPublishDate(post.datetime) }}</time>
          <time class="post_time text-white text-lg mb-2 uppercase font-medium ml-40">Time: {{ formatPublishTime(post.datetime) }}</time>
          <button class="btn_upcoming">Upcoming</button>
        </header>
        <p class="post_desc leading-normal text-white text-lg px-2" v-html="excerpt(post, 280, ' ...')"></p>
        <button class="btn_read_more"><a :href="post.path">Read More</a></button>
      </div>
    </div>
  </article>
</template>

<script>
import moment from 'moment'

export default {
  props: ['post'],
  computed: {
    formattedPublishDate() {
      return moment(this.post.date).format('DD MMMM, YYYY');
    },
    formattedPublishTime() {
      return moment(this.post.time).format('h:m:s');
    },
    imagePath () {
      return this.post.image;
    },
  },
  methods: {
    formatPublishDate(date) {
      return moment(date).format('DD MMMM, YYYY');
    },
    formatPublishTime(time) {
      return moment(time).format('h:m:s');
    },
    excerpt(post, length, clamp) {
      if (post.excerpt) {
        return post.excerpt
      }

      length = length || 280
      clamp = clamp || ' ...'
      let text = post.content.replace(/<pre(.|\n)*?<\/pre>/gm, '').replace(/<[^>]+>/gm, '')

      return text.length > length ? `${ text.slice(0, length)}${clamp}` : text
    },
    titleCase(str) {
      return str.replace('-', ' ').split(' ').map((s) => s.charAt(0).toUpperCase() + s.substring(1)).join(' ')
    }
  },
}
</script>
