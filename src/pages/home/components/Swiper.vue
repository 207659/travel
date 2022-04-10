<template>
<div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
        <swiper-slide v-for="item of swiperList" :key="item.id"><img class="swiper-img" :src="item.imgUrl" /></swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
</div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    props: {
        swiperList: Array
    },
    data () {
        return {
            swiperOption:{
                pagination:'.swiper-pagination',
                loop: true,
                speed: 1000,
				autoplay: 3000
            },
            // swiperList:[
            //     {id:'0001',imgUrl:'https://cdn.pixabay.com/photo/2020/12/17/14/07/flowers-5839544_960_720.jpg'},
            //     {id:'0002',imgUrl:'https://cdn.pixabay.com/photo/2021/07/01/21/19/hat-6380330_960_720.jpg'}
            // ]
        }
    },
    computed: {
        showSwiper () {
            return this.swiperList.length
        }
    }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
    background:rgba(255,255,255,.8)
.wrapper
    overflow:hidden
    width:100%
    height:0
    padding-bottom:31.25%
    background:#eee
    .swiper-img
        width:100%
    .swiper-pagination
        top: 1.9rem
</style>
  