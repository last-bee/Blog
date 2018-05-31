<template>
  <div id="app">
    <m-header @clickNavIcon = 'clickNavIcon'></m-header>
    <m-left :show='leftShow' @modalClick = 'modalClick'></m-left>
    <router-view/>
  </div>
</template>

<script>
import MHeader from 'components/m-header/m-header'
import MLeft from 'components/m-left/m-left'
export default {
  name: 'App',
  components:{MHeader,MLeft},
  data(){
    return{
      leftShow:false
    }
  },
  methods:{
    clickNavIcon(){
      this.leftShow = true
    },
    modalClick(){
      this.leftShow = false
    }
  }
}
</script>

<style  lang="stylus">
#app
  width:100%
  height:100%
  position relative
</style>
