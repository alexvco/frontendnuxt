<template>
  <div>
    <h1>Images</h1>
    <v-search-image v-on:search-text="searchForImage" />
    <v-pic v-for="pic in pics" :key="pic.id" :id="pic.id" :picfilename="pic.attributes.filename" />
  </div>
</template>

<script>
import axios from 'axios'
import Pic from '~/components/Pic'
import SearchImage from '~/components/SearchImage'

export default {
  components: {
    vPic: Pic,
    vSearchImage: SearchImage
  },
  data() {
    return {
      pics: []
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }

    try {
      const res = await axios.get('http://localhost:3000/api/v1/images', config)
      this.pics = res.data.data
    } catch (err) {
      console.log(err)
    }
  },
  methods: {
    async searchForImage(text) {
      const config = {
        headers: {
          Accept: 'application/json'
        }
      }

      try {
        const res = await axios.get(`http://localhost:3000/api/v1/images?term=${text}`, config)
        this.pics = res.data.data
      } catch (err) {
        console.log(err)
      }
    }
  },
  head() {
    return {
      title: 'Images',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'This is the images page'
        }
      ]
    }
  }
}
</script>

<style>

</style>
