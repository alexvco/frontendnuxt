<template>
  <div>
    <v-app-header />
    <nuxt />
  </div>
</template>

<script>
import AppHeader from '~/components/AppHeader'

export default {
  components: {
    vAppHeader: AppHeader
  }
}
</script>

<style>

</style>
