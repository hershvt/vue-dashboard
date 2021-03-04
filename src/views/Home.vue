<template>
  <div class="container-fluid">
    <div class="main">
      Hello World
    </div>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'


export default {
  name: 'Home',
  components: {
    HelloWorld,

  }
}
</script>

<style scoped>
.main{
    background: linear-gradient(to right,#0acffe 0,#495aff 100%);
    color: #fff;
    font-family: Helvetica;
    font-weight: 600;
    font-size: 50px;
    text-align: center;
    height: 200px;
    
}
</style>