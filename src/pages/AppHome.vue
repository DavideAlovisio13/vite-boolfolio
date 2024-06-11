<template>
    <div>
      <CardComponent v-for="project in projects" :key="project.id" :name="project.name" :project="project"/>
    </div>
    <carousel :items-to-show="5">
      <slide v-for="project in projects" :key="project.id">
        {{ project.name }}
      </slide>
  
      <template #addons>
        <navigation />
        <pagination />
      </template>
    </carousel>
  </template>
  
  <script>
  import axios from 'axios'
  import {store} from './components/store.js'
  import CardComponent from './pages/CardComponent.vue';
  import 'vue3-carousel/dist/carousel.css'
  import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
    export default {
      name: 'App',
      components: {
        CardComponent,Carousel, Slide, Pagination, Navigation
      },
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