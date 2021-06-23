<template>
  <Layout>
    <div>
      <HeaderNav />
    </div>
    <main class="bg-current" style="padding-top:100px;">
      <div class="bg-black" id="new_body">
        <img src="@/assets/images/webinar-software_2.png" id="new_main_img" />
        <div class="grid grid-rows-3" style="max-width: 67%">
          <div class="col-span-2" style="border:2px solid white;">
            <div class="flex" id="new_main_header">
              <h1 class="text-white" id="new_main_title">Providing Great Technology into the Future.</h1>
            </div>
            <div class="flex">
              <button class="btn_upcoming" style="float:left !important;margin-left:30px;">Upcoming</button>
              <p class="text-white" style="font-size:22px;margin-top:-8px;margin-left:50px;">Date: 5th January, 2020</p>
              <p class="text-white" style="font-size:22px;margin-top:-8px;margin-left:50px;">Time: 19:00 - 22:00</p>
              <p style="display:flex;margin-left:50px; "><svg width="17" height="18" viewBox="0 0 17 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M0 9C0 10.654 1.346 12 3 12C3.794 12 4.512 11.685 5.049 11.18L11.04 14.604C11.022 14.734 11 14.864 11 15C11 16.654 12.346 18 14 18C15.654 18 17 16.654 17 15C17 13.346 15.654 12 14 12C13.206 12 12.488 12.315 11.951 12.82L5.96 9.397C5.978 9.266 6 9.136 6 9C6 8.864 5.978 8.734 5.96 8.603L11.951 5.18C12.488 5.685 13.206 6 14 6C15.654 6 17 4.654 17 3C17 1.346 15.654 0 14 0C12.346 0 11 1.346 11 3C11 3.136 11.022 3.266 11.04 3.397L5.049 6.82C4.496 6.29468 3.76273 6.00123 3 6C1.346 6 0 7.346 0 9Z" fill="#EB5424"/>
                  </svg><p style="font-size: 20px;margin-left: 10px;color: #EB5424;margin-top: -5px;">Share</p>
              </p>
              <div class="flex" style="margin-left: 50px;">
                <svg width="22" height="18" viewBox="0 0 22 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                <g clip-path="url(#clip0)">
                <path d="M22 2.18727C21.1905 2.54623 20.3206 2.78883 19.4076 2.89797C20.3396 2.33938 21.0552 1.45482 21.3922 0.400887C20.5062 0.92664 19.5369 1.29707 18.5261 1.49616C17.7027 0.618996 16.5297 0.0708008 15.2315 0.0708008C12.7388 0.0708008 10.7178 2.09171 10.7178 4.58424C10.7178 4.93804 10.7577 5.28248 10.8347 5.61291C7.08348 5.42462 3.7577 3.62775 1.53149 0.897004C1.14305 1.56362 0.920477 2.33904 0.920477 3.1661C0.920477 4.73205 1.71738 6.1135 2.92841 6.92294C2.21164 6.90049 1.51065 6.7069 0.883953 6.35833C0.883695 6.37724 0.883695 6.39615 0.883695 6.41514C0.883695 8.60199 2.43951 10.4263 4.50424 10.8409C3.83959 11.0217 3.14242 11.0481 2.46598 10.9183C3.0403 12.7114 4.70723 14.0163 6.68224 14.0528C5.13752 15.2633 3.19129 15.985 1.07671 15.985C0.712336 15.985 0.353117 15.9636 0 15.9219C1.99745 17.2025 4.36992 17.9498 6.91883 17.9498C15.221 17.9498 19.7608 11.0721 19.7608 5.10768C19.7608 4.91192 19.7565 4.71727 19.7478 4.52374C20.6314 3.88495 21.3941 3.09375 22 2.18727Z" fill="#55ACEE"/>
                </g>
                <defs>
                <clipPath id="clip0">
                <rect width="22" height="17.9609" fill="white"/>
                </clipPath>
                </defs>
                </svg>
                <p style="color:#55ACEE; font-size: 20px; margin-top: -5px;margin-left: 10px;">Share In Twitter</p>
              </div>
            </div>
            <div style="padding: 30px;color:white;">
              <p>
                Do you wish that your e-commerce website can be fast, secure, responsive, cross-browser compatible, plus work offline and act like a native app on mobile?<br/><br/>

                See how GoMage, a Magento Development company and one of our key partners, helps businesses prepare for the future of e-commerce with Magento themes that are easy to install, maintain, and customize, on DigitalOcean’s powerful server infrastructure. In this Talk, Yuriy Protsiuk, a product owner at the GoMage Magento PWA Theme, will present a customer case study showcasing real-time benefits and the results yielded from onboarding GoMage and DigitalOcean.<br/><br/>

                Together with Austin Black, Solutions Engineer at DigitalOcean, Yuriy will deep dive into the GoMage tech stack based on DigitalOcean servers. They will also cover the benefits of progressive web applications for the e-commerce business. Lastly, this Tech Talk will feature a demo of the GoMage Magento 2 PWA Theme, a plug-and-play solution that helps quickly add a PWA storefront to a Magento 2 website.
              </p>
            </div>
          </div>
          <div class="col-span-7">
          </div>
        </div>
      </div>
      <site-footer class="pb-8 sm:pb-10" />
    </main>
  </Layout>
</template>

<script>
import config from '~/.temp/config.js'
import SiteFooter from '@/components/Footer'
import HeaderNav from '@/components/HeaderNav'
export default {
  components: {
    SiteFooter,
    HeaderNav
  },
  metaInfo () {
    return {
      title: 'New',
      meta: [
        {
          key: 'description',
          name: 'description',
          content: this.ogDescription
        },

        { property: "og:type", content: 'article' },
        { property: "og:title", content:'About' },
        { property: "og:description", content: this.ogDescription },
        { property: "og:url", content: `${this.config.siteUrl}/about/` },
        { property: "og:image", content: this.ogImageUrl },

        { name: "twitter:card", content: "summary_large_image" },
        { name: "twitter:title", content: 'About' },
        { name: "twitter:description", content: this.ogDescription },
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
    ogDescription () {
      return 'Introduction to the Bleda blog starter for Gridsome.'
    },
    ogImageUrl () {
      return `${this.config.siteUrl}/images/bleda-card.png`
    }
  },
}
</script>
