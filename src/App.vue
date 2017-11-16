<template>
  <div id="app">
    <tab></tab>
    <router-view></router-view>
    
  </div>
  
</template>

<script>

import tab from "@/components/tab/tab"
export default {
  name:'app',
  components:{
    tab
    }
}


</script>

<style>
#app{
  height:100%;
}
</style>
