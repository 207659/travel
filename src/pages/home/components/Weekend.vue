<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
                <div class="item-img-wrapper"><img class="item-img" :src="item.imgUrl" /></div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>                
            </li>
        </ul>
    </div>
</template>
    
<script>
export default {
    name: 'HomeWeekend',
    props: {
        weekendList: Array
    },
    data () {
        return {
            // weekendList:[
            //     {id:'0001',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/03/25/13/47/flowers-7091131_960_720.jpg'},
            //     {id:'0002',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/03/25/13/47/flowers-7091131_960_720.jpg'},
            //     {id:'0003',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/03/25/13/47/flowers-7091131_960_720.jpg'},
            // ]
        }
    }
}
</script>
    
<style lang="stylus" scoped>
@import '~styles/mixins.styl';
.title
    line-height:.8rem
    background:#eee
    text-indent:.2rem
.border-bottom
    border-bottom: .01rem solid #eaeaea
.item-img-wrapper
    overflow:hidden
    height:0
    padding-bottom:37.09%
    .item-img
        width:100%
.item-info
    padding:.1rem
    .item-title
        line-height:.54rem
        font-size:.32rem
        ellipsis()
    .item-desc
        line-height:.4rem
        color:#ccc
        ellipsis()

</style>
      