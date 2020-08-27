<template>
  <div id="app">
    <main-search />
  </div>
</template>

<script>
import MainSearch from '@/pages/MainSearch'

export default {
  name: 'App',
  components: {
    MainSearch
  }
}
</script>

<style lang="scss">
@import "~bulma/css/bulma.css"
</style>
