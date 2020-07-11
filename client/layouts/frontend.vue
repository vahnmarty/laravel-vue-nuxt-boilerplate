<template>
  <div class="layout">
    <navbar />

    <div class="site-content py-5">
    	 <nuxt />
    </div>
    

    <site-footer/>

  </div>

</template>

<script>
import Navbar from '~/components/frontend/Navbar'
import SiteFooter from '~/components/frontend/Footer'

export default {
  components: {
    Navbar, 
    'site-footer': SiteFooter
  }
}
</script>
