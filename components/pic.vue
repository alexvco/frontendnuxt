<template>
  <nuxt-link :to="'images/' + id">
    <div>
      <p>{{ picfilename }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Pic',
  props: {
    picfilename: {
      type: String,
      required: false,
      default: ''
    },
    id: {
      type: String,
      required: false,
      default: ''
    }
  }
}
</script>

<style>

</style>
