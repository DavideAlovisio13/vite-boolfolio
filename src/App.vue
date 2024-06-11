<template>
  <div>
    <router-view></router-view>
  </div>
</template>

<script>
import axios from 'axios'
import {store} from './components/store.js'
export default {
  data() {
    return {
      projects: []
    };
  },
}
</script>

<style lang="scss" scoped></style>