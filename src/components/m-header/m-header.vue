<template>
  <div class="m-header">
    <div class="nav-icon" @click="clickNavIcon">
        <span class="nav-top"></span>
        <span class="nav-bottom"></span>
    </div>
    <div class='nav'>
      <div>首页</div>
      <div>点滴</div>
      <div>总结</div>
      <div>生活</div>
    </div>
  </div>
</template>

<script>
  export default {
    methods:{
      clickNavIcon(){
        this.$emit('clickNavIcon')
      }
    }
  }
</script>

<style scoped lang='stylus'>
@import '~common/stylus/variable'
@import '~common/stylus/mixin'
.m-header
  min-width:1024px
  margin 0 auto
  height 44px
  box-shadow: 0 1px 3px rgba(0,0,0,.3);
  background :$color-theme 
  .nav-icon
    width:50px
    height 44px
   
    flex-direction column
    justify-content center
    align-items center
    display none
    span  
      width 17px
      height 1px
      background #fff
      display block
    .nav-top
      margin-bottom 6px
  .nav
    width:1024px
    margin 0 auto 
    display flex
    padding 0 20px
    align-items center
    height 100%
    color #fff
    div
      flex 1
      justify-content space-around
      text-align center
      &:hover
        color #b3abab
@media screen and (max-width :1024px){
  .nav{
    display:none !important
  }
 
  .nav-icon{
    display flex !important
  }
  
}
</style>