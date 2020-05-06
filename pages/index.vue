<template>
  <div class="container">
    <div @click="toggleTheme">
      Toggle the theme
    </div>
  </div>
</template>

<script>
import Cookies from 'js-cookie'

export default {
  methods: {
    toggleTheme () {
      let newTheme
      if (document.body.classList.contains('theme-dark')) {
        // toggle to light theme
        document.body.classList.replace('theme-dark', 'theme-light')
        newTheme = 'light'
      } else {
        // toggle to dark theme
        document.body.classList.replace('theme-light', 'theme-dark')
        newTheme = 'dark'
      }
      // set a cookie for ssr purposes
      Cookies.set('theme', newTheme)
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: var(--font-color);
}
</style>
