<template>
  <form @submit.prevent="submitSearch">
    <input type="text" v-model="imagetext" name="" placeholder="Search Images...">
    <input type="submit" name="" value="Search">
  </form>
</template>

<script>
export default {
  name: 'SearchImage',
  data() {
    return {
      imagetext: ''
    }
  },
  methods: {
    submitSearch() {
      this.$emit('search-text', this.imagetext)
      this.imagetext = ''
    }
  }
}
</script>

<style>

</style>
