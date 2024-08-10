<template>
  <Client/>
  <api/>
</template>

<script>
import Client from './components/ClientComponent.vue'
import api from './components/ApiComponent.vue'

export default {
  name: 'App',
  components: {
    Client,
    api
  },
  data(){
    return{
      testbe:'davida'

    }
  },
  methods:{
    test(){
      console.log("test  bes")
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
