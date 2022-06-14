<template>
  <div>    
    <div>
      <my-list/>

    </div>
  </div>
</template>

<script>

import List from '@/components/List.vue'
export default {
  name: 'App',
  data(){
    return{
     
    }
  },
  components: {
    "my-list":List,
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
