<template>
  <Client/>
</template>

<script>
import Client from './components/ClientComponent.vue'

export default {
  name: 'App',
  components: {
    Client
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
