<template>
  <header class="app-header navbar">
      <button class="navbar-toggler sidebar-toggler d-lg-none mr-auto" type="button" data-toggle="sidebar-show">
          <span class="navbar-toggler-icon"></span>
      </button>
      <a class="navbar-brand bg-dark-primary d-none d-lg-block" href="#">
          <img class="navbar-brand-full" :src="logo" height="40" />
      </a>

      <a href="#!" class="sidebar-minimizer brand-minimizer ml-3">
          <span class="fa fa-bars text-dark"></span>
      </a>

      <button class="navbar-toggler sidebar-toggler d-md-down-none d-none" type="button" data-toggle="sidebar-lg-show">
          <span class="navbar-toggler-icon"></span>
      </button>


      <ul class="nav navbar-nav ml-auto">
          <li class="nav-item dropdown mr-4">
            <a href="#!"  data-toggle="dropdown">
                <i class="fa fa-envelope-o text-dark fa-lg"></i>
            </a>
          </li>
          <li class="nav-item dropdown mr-4">
            <a href="#!"  data-toggle="dropdown">
                <i class="fa fa-bell-o text-dark  fa-lg"></i>
            </a>
          </li>
          <li class="nav-item mr-3">
              <a class="img-avatar d-inline-block">
                  <img :src="photo_url"  alt="Email" width="100%" />
              </a>
          </li>
          <li class="nav-item">
              <a href="logout"   @click.prevent="logout">
                  <i class="fa fa-sign-out text-dark  fa-lg"></i>
              </a>
          </li>
      </ul>

      <button class="navbar-toggler aside-menu-toggler d-md-down-none" type="button" data-toggle="aside-menu-lg-show">
          <span class="navbar-toggler-icon"></span>
      </button>


  </header>
</template>

<script>
  import { mapGetters } from 'vuex'
  export default {

    data: () => ({
      logo:require('@/assets/images/logo.svg'),
      photo_url: ''
    }),

    created () {
      this.photo_url = this.user.photo_url
    },

    computed: mapGetters({
      user: 'auth/user'
    }),
  }
</script>