<template>
  <div class="card mb-4">
    <div class="card-content">
      <p class="mb-2"><small>Posted by: <b>{{postData.data.author}}</b></small></p>
      <p class="mb-2" v-if="postData.data.distinguished">
        <span class="has-background-grey-lighter px-2">Moderador</span>
      </p>
      <p class="mb-4">{{postData.data.title}}</p>
      <span class="px-2 py-1 mt-3 has-background-info has-text-white-bis"><small>up-votes: <b>{{postData.data.ups}}</b></small></span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'SingleCard',
  props: {
    postData: Object,
    required: true
  }
}
</script>
<style lang="scss">
  span {
    border-radius: 2em;
  }
</style>