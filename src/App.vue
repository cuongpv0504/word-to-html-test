<template>
  <div>Convert to HTML</div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <HtmlPreview></HtmlPreview>
</template>

<script>
import HtmlPreview from '@/components/HtmlPreview'

export default {
  name: 'App',
  components: {
    HtmlPreview
  }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
