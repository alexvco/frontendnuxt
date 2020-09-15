<template>
  <header>
    <h1>Frontendnuxt</h1>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/images">Images</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style>

li {
  list-style: none;
  display: inline-block;
}
.header ul {
  display: flex;
}
.header a {
  display: inline-block;
}
</style>
