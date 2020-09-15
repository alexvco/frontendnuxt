<template>
  <div>
    <nuxt-link to="/images">Back to images</nuxt-link>
    <h3>Image id: {{ $route.params.id }}</h3>
    <h3>Image type: {{ pic.type }}</h3>
    <h3>Image filename: {{ pic.attributes.filename }}</h3>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      pic: {}
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }

    try {
      const res = await axios.get(`http://localhost:3000/api/v1/images/${this.$route.params.id}`, config)
      this.pic = res.data.data
    } catch (err) {
      console.log(err)
    }
  },
  head() {
    return {
      title: this.pic.attributes.filename,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: `This is the description for image id: ${this.pic.id}`
        }
      ]
    }
  }
}
</script>

<style>

</style>
