<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="https://cdn.pixabay.com/photo/2022/03/06/06/42/flowers-7050948_960_720.jpg" />
            <div class="banner-info">
                <div class="banner-title">大连圣亚海洋世界（AAAA景区）</div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe67f;</span>39</div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>    
</template>
  
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
    name: 'DetailBanner',
    components: {
        CommonGallary
    },
    data () {
        return {
            showGallary: false,
            imgs: [
            'https://cdn.pixabay.com/photo/2022/03/06/06/42/flowers-7050948_960_720.jpg',
            'https://cdn.pixabay.com/photo/2021/07/01/21/19/hat-6380330_960_720.jpg'
            ]
        }
    },
    methods:{
        handleBannerClick () {
            this.showGallary = true
        },
        handleGallaryClose () {
            this.showGallary = false
        }
    }
}
</script>
  
<style lang="stylus" scoped>
.banner
    position:relative
    overflow:hidden
    height:0
    padding-bottom:55%
    .banner-img
        width:100%
    .banner-info
        display:flex
        position:absolute
        left:0
        right:0
        bottom:0
        line-height:.6rem
        color:#fff
        background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
        .banner-title
            flex:1
            font-size:.32rem
            padding:0 .2rem
        .banner-number
            padding:0 .4rem
            height:.32rem 
            line-height:.32rem
            margin-top:.14rem
            border-radius:.2rem
            background:rgba(0, 0, 0, .8)
            font-size:.24rem
            .banner-icon
                font-size:.24rem
</style>
  