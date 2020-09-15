<template>
  <div class="container">
    <h1>An error occurred: {{ error.message }}</h1>
    <nuxt-link to="/">Home page</nuxt-link>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'default'
}
</script>
