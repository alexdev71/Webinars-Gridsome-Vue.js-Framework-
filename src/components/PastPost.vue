<template>
  <article>
    <div class="past_article_main my-8 bg-current" style="border-radius:15px;">
      <g-image :src="imagePath" class="past_software_images" />
      <div class="ml-8 py-4">
        <header class="">
          <h2 class="text-2xl sm:text-3xl leading-tight font-sans mb-1 sm:mb-2">
            <g-link :to="`${post.path}/`" class="text-white">{{ post.title }}</g-link>
          </h2><br/>
        </header>
        <p class="post_desc leading-normal text-white text-lg px-2" v-html="excerpt(post, 280, ' ...')"></p>
        <button id="btn_view_video">View Archived Video</button>
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
