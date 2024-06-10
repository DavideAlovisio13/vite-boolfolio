<template>
  <div>
    <ul>
      <li v-for="project in projects" :key="project.id">{{ project.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
import {store} from './components/store'
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
        axios.get('http://127.0.0.1:8000/api/projects').then((response) => {
          this.projects = response.results;
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