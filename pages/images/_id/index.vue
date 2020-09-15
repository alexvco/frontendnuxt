<template>
  <div>
    <nuxt-link to="/images">Back to images</nuxt-link>
    <h3>Image id: {{ $route.params.id }}</h3>
    <h3>Image type: {{ pic.type }}</h3>
    <h3>Image filename: {{ pic_attributes.filename }}</h3>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      pic: {},
      pic_attributes: {}
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
      this.pic_attributes = res.data.data.attributes // for some reason i had to resort to this as nested attributes of pic was erroring out on page refresh
    } catch (err) {
      console.log(err)
    }
  },
  head() {
    return {
      title: this.pic_attributes.filename,
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
