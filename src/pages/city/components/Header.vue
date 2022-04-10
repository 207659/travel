<template>
    <div class="header">
      城市选择
        <router-link to="/">
            <div class="iconfont back-icon">&#xe624;</div>
        </router-link>
    </div>
</template>
  
  <script>
  export default {
    name: 'CityHeader',
    data () {
      return {
        
      }
    },
    methods:{
        
    }
  }
  </script>
  
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.header
    position:relative
    overflow:hidden
    height: $header_height
    line-height: $header_height
    text-align:center
    color:#fff
    background:$bg_color
    font-size:.32rem
    .back-icon
        position:absolute
        top:0
        left:0
        width:.64rem
        text-align:center
        font-size:.4rem
        color:#fff
</style>
  