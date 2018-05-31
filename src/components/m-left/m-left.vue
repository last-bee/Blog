<template>
<transition name='fadeIn'>
  <div class="modal" v-show="show" @click='modalClick'>

  
    <transition name='slideRight'>
      <div class="nav-left" v-show='show'>
        <div class="nav-main">
            <div>首页</div>
            <div>点滴</div>
            <div>总结</div>
            <div>生活</div>
        </div>
      </div>
    </transition>
  </div>
</transition>
</template>

<script>
  export default {
    props:{
      show:{
        type:Boolean,
        default:false
      }
    },
    methods:{
      modalClick(){
        this.$emit('modalClick')
      }
    }
  }
</script>

<style scoped lang='stylus'>
.slideRight-enter-active, .slideRight-leave-active
  transition: all .3s
.slideRight-enter,.slideRight-leave-to
  transform: translate3d(-100%, 0%, 0)
.fadeIn-enter-active, .fadeIn-leave-active
  transition: all .3s
.slideDown-enter,.slideDown-leave-to
  opacity 0
.nav-left
  position absolute
  top:0
  bottom 0
  left 0
  right:0%
  background #000
  padding:0 48px
.modal
  position fixed
  top 0px
  bottom 0
  left 0
  right 0
  background rgba(0,0,0,.5)
.nav-main
  display flex
  width:100%
  flex-wrap: wrap 
  div
    width:100%
    height 44px
    line-height 44px
    color:#fff
    font-size:18px
    border-bottom 1px solid  rgb(51,51,51)
    &:hover
      color #b3abab
</style>