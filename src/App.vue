<template>
  <div id="app">
    <mytitle class="title"></mytitle>
     <router-view  class="router"></router-view>
     <playback class="ctx"></playback>
  </div>
</template>

<script>
import mytitle from "./components/title.vue"
import Playback from "./components/Playback.vue"
export default {
  name: 'Home',
  components: {
    mytitle:mytitle,
    playback:Playback
  },
  data(){
    return {}
  },
  methods:{
    
  }
}
</script>
<style lang="scss">
*{
    user-select:none;
}
#app{
   display: flex;
   flex-direction: column;
   width:100%;
   height: 100%;
   background: blue;
   .title{
      width:100%;
      height:80px;
   }
   .router{
     width:100%;
     height:200px;
     flex:1;
     background: wheat;
   }
   .ctx{
     width:100%;
     height:3.5rem;
   }
}
</style>
