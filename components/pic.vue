<template>
  <div>
    <p>{{ picfilename }}</p>
  </div>
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
