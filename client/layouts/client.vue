<template>
  <div class="backend-layout">
  	<div class="app header-fixed sidebar-fixed aside-menu-off-canvas sidebar-lg-show bg--primary">

  		<Navbar/>

  		<div class="app-body">
         <sidebar/>


  			<main class="main pt-3 main-container app-container">
  				<div class="container-fluid">

  					<nuxt />
  				</div>
  			</main>
  		</div>
  	</div>	
  	
  </div>
</template>

<style lang="sass">
  @import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css')
</style>

<script>
import { mapGetters } from 'vuex'
import Navbar from '@/components/client/Header'
import Sidebar from '@/components/client/Sidebar'
export default {

  data: () => ({
    logo:require('../assets/images/logo.svg'),
    auth:"",
    photo_url:"",
    title: 'Tuning Software'
  }),

  components:{
    Navbar,
      'sidebar': Sidebar
  },



  computed: mapGetters({
    user: 'auth/user'
  }),

  created () {
    this.photo_url = this.user.photo_url;
  },

  methods: {
    async logout () {
      // Log out the user.
      await this.$store.dispatch('auth/logout')

      // Redirect to login.
      this.$router.push({ name: 'login' })
    }
  }
}
</script>
