<template>
  <card :title="$t('home')">
    {{ $t('you_are_logged_in') }}
  </card>
</template>

<script>
export default {
  middleware: 'auth',
  layout: 'client',
  
  head () {
    return { title: this.$t('home') }
  }
}
</script>
