<template>
  <div>
    <h1>Images</h1>
    <pic v-for="pic in pics" :key="pic.id" :id="pic.id" :picfilename="pic.attributes.filename" />
  </div>
</template>

<script>
import axios from 'axios'
import pic from '../../components/pic'

export default {
  components: {
    pic
  },
  data() {
    return {
      pics: []
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json',
        'Access-Control-Allow-Origin': '*',
        'Access-Control-Allow-Headers': '*'
      }
    }

    try {
      const res = await axios.get('http://localhost:3000/api/v1/images', config)
      this.pics = res.data.data
    } catch (err) {
      console.log(err)
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
