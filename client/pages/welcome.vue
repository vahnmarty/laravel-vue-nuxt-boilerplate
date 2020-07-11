<template>
  <div>
    <section class="site-section hero-banner bg-light">
      <div class="container">
        <div class="row">
          <div class="col-lg-6 align-self-center">
            <div class="text-left">
              <h1 class="h1 mb-0 title">
                <span class="laravel">Laravel</span><span>-Vue-</span><span class="nuxt">Nuxt</span>
              </h1>
              <h1>Boilerplate</h1>
              <div class="links">
                <a href="https://github.com/vahnmarty/laravel-vue-nuxt-boilerplate">https://github.com/vahnmarty/laravel-vue-nuxt-boilerplate</a>
              </div>
              <hr style="width: 70%;" class="ml-0">
              <p class="lead">Laravel 7 with VueJs using NuxtJS Framework. <br>Ready-to-use for Full Stack Developers</p>
              <ul>
                <li v-for="feature in features">{{ feature }}</li>
              </ul>
            </div>
          </div>
          <div class="col-lg-5 offset-lg-1">
            <img :src="vector">
          </div>
        </div>
      </div>
    </section>
    
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  layout: 'frontend',

  head () {
    return { title: this.$t('home') }
  },

  data: () => ({
    title: process.env.appName,
    vector: require('assets/images/website-setup-animate.svg'),
    features: [
      "Bootstrap 4", "SASS with ITCSS", "Ready-made Frontend Pages", "Basic Auth using API", "Admin Dashboard and Basic Features", "Helpers", "Laravel Modules"
    ]
  }),

  computed: mapGetters({
    authenticated: 'auth/check'
  })
}
</script>

<style scoped>
.top-right {
  position: absolute;
  right: 10px;
  top: 18px;
}

.title {
  font-size: 45px;
}

.laravel {
  color: #2e495e;
}

.nuxt {
  color: #00c48d;
}
</style>
