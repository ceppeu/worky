<template>
  <div class="container">
    <hero />
    <div class="field mb-6">
      <label class="label">Filtrar por personaje personaje</label>
      <div class="control">
        <div class="select">
          <select v-model="filter">
            <option selected>Sin filtro</option>
            <option value="Frodo">Frodo</option>
            <option value="Bilbo">Bilbo</option>
            <option value="Sam">Sam</option>
            <option value="Merry">Merry</option>
            <option value="Pippin">Pippin</option>
            <option value="Gollum">Gollum</option>
          </select>
        </div>
      </div>
    </div>
    <div v-for="post in postsData" :key="post.id">
      <single-card :postData="post" />
    </div>
  </div>
</template>
<script>
import Hero from '@/components/Hero'
import SingleCard from '@/components/SingleCard'
import axios from 'axios'

export default {
  name: 'MainSearch',
  components: {
    Hero,
    SingleCard
  },
  data: function() {
    return {
      postsData: '',
      filter: ''
    }
  },
  watch: {
    filter: function(value) {
      let options = {
        method: 'GET',
        url: 'https://www.reddit.com/r/lotr.json',
        params: {
          limit: 100
        }
      }
      if (value !== 'Sin filtro') {
        options = {
          method: 'GET',
          url: `https://www.reddit.com/search.json?q=${value}+subreddit:lotr`
        }
      }
      this.getData(options)
    }
  },
  created: async function () {
    const options = {
      method: 'GET',
      url: 'https://www.reddit.com/r/lotr.json',
      params: {
        limit: 100
      }
    }
    this.getData(options)
  },
  methods: {
    getData: function (options) {
      axios({
        method: options.method,
        url: options.url,
        params: options.params
      })
      .then(response => {
        console.log(response.data)
        const { data } = response
        this.postsData = data.data.children
      })
      .catch(error => {
        console.log('Error', error)
      })
    }
  }
}
</script>