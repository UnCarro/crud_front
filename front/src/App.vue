<template>
  <div id="app">
    <Header title="CRUD Try"/>
   
    <router-view/>

  </div>
</template>

<script>
import Vue from 'vue'
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Header from './components/Header.vue'

Vue.use(BootstrapVue)
Vue.use(IconsPlugin)

export default({
  name: 'app',
  components: {
    Header
  }
})
</script>


