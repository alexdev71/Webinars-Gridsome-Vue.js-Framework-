<template>
  <Layout class="font-sans bg-current">
    <div>
      <HeaderNav />
    </div>
    <main>
      <header>
        <div class="max-w-xl md:max-w-3xl xl:max-w-4xl mx-auto text-center px-6 border-b border-gray-300 my-12">
          <div id="oval"></div>
          <div id="left_gradient"></div>
          <h2 class="text-2xl sm:text-2xl md:text-6xl font-sans font-bold mb-1" style="font-size:36px;">
            <g-link to="/" class="text-white">Upcoming Webinars</g-link>
          </h2>
        </div>
      </header>
      <section id="home_main">
        <post-item v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node" />
        <div>
          <div id="oval_2">
          </div>
          <div id="left_gradient_2" style=""></div>
        </div>
      </section>
      <button class="btn_show_more" style="margin-bottom: 50px;">Show More</button>
      <section class="bg-black">
          <div id="oval_3"></div>
          <div id="right_gradient"></div>
        <div class="max-w-xl md:max-w-3xl xl:max-w-4xl mx-auto border-b border-gray-300">
          <center><h2 class="text-2xl sm:text-2xl md:text-5xl font-sans font-semibold mb-1 text-white py-10">Past Webinars</h2></center>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3" style="" id="past_post_view">
          <past-post v-for="edge in $page.pastposts.edges" :key="edge.node.id" :post="edge.node" />
        </div>
        <button class="btn_show_more" style="margin-top:50px;margin-bottom: 150px;">Show More</button>
      </section>
      <site-footer class="pb-8 sm:pb-10" />
    </main>
  </Layout>
</template>

<script>
import config from '~/.temp/config.js'
import SiteFooter from '@/components/Footer'
import PostItem from '@/components/PostItem'
import PastPost from '@/components/PastPost'
import Pagination from '@/components/Pagination'
import HeaderNav from '@/components/HeaderNav'
export default {
  components: {
    HeaderNav,
    PostItem,
    PastPost,
    Pagination,
    SiteFooter,
  },
  metaInfo () {
    return {
      title: this.$static.metadata.siteName,
      meta: [
        { property: "og:type", content: 'website' },
        { property: "og:title", content: this.$static.metadata.siteName },
        { property: "og:description", content: this.$static.metadata.siteDescription },
        { property: "og:url", content: this.$static.metadata.siteUrl },
        { property: "og:image", content: this.ogImageUrl },

        { name: "twitter:card", content: "summary_large_image" },
        { name: "twitter:title", content: this.$static.metadata.siteName },
        { name: "twitter:description", content: this.$static.metadata.siteDescription },
        { name: "twitter:site", content: "@cossssmin" },
        { name: "twitter:creator", content: "@cossssmin" },
        { name: "twitter:image", content: this.ogImageUrl },
      ],
    }
  },
  computed: {
    config () {
      return config
    },
    ogImageUrl () {
      return `${this.config.siteUrl}/images/bleda-card.png`
    }
  },
}
</script>

<page-query>
  query Home ($page: Int) {
    posts: allPost (page: $page, perPage: 6) @paginate {
      totalCount
      pageInfo {
        totalPages
        currentPage
      }
      edges {
        node {
          id
          title
          timeToRead
          datetime: date (format: "YYYY-MM-DD HH:mm:ss")
          content
          excerpt
          description
          path
          cover
          image
          tags {
            id
            title
            path
          }
          author {
            id
            title
            path
          }
        }
      }
    }
    pastposts: allPastPost {
      totalCount
      pageInfo {
        totalPages
        currentPage
      }
      edges {
        node {
          id
          title
          timeToRead
          datetime: date (format: "YYYY-MM-DD HH:mm:ss")
          content
          excerpt
          description
          path
          cover
          image
          tags {
            id
            title
            path
          }
          author {
            id
            title
            path
          }
        }
      }
    }
  }
</page-query>


<static-query>
query {
  metadata {
    siteName
    siteUrl
    siteDescription
  }
}
</static-query>
