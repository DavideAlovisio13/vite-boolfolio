<template>
  <div>
    <ul>
      <li v-for="project in projects" :key="project.id">{{ project.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
import {store} from './components/store.js'
  export default {
    name: 'App',
    data() {
      return {
        store,
        projects: []
      }
    }, 
    methods: {
      getApi() {
        axios.get(this.store.baseUrl + '/projects').then((response) => {
          this.projects = response.data.results;
        })
      }
    },
    mounted() {
      this.getApi()
      console.log(this.projects)
    }
  }
</script>

<style lang="scss" scoped>

</style>