<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <router-link tag="li" class="item border-bottom" v-for="item of recommendList" :key="item.id" :to="'/detail/'+item.id">
                <img class="item-img" :src="item.imgUrl" />
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-btn">查看详情</button>
                </div>                
            </router-link>
        </ul>
    </div>
</template>
    
<script>
export default {
    name: 'HomeRecommend',
    props: {
        recommendList: Array
    },
    data () {
        return {
            // recommendList:[
            //     {id:'0001',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/02/12/13/29/desert-7008952_960_720.jpg'},
            //     {id:'0002',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/02/12/13/29/desert-7008952_960_720.jpg'},
            //     {id:'0003',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/02/12/13/29/desert-7008952_960_720.jpg'},
            //     {id:'0004',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/02/12/13/29/desert-7008952_960_720.jpg'},
            //     {id:'0005',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/02/12/13/29/desert-7008952_960_720.jpg'},
            //     {id:'0006',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题乐园',imgUrl:'https://cdn.pixabay.com/photo/2022/02/12/13/29/desert-7008952_960_720.jpg'},
            // ]
        }
    }
}
</script>
    
<style lang="stylus" scoped>
@import '~styles/mixins.styl';
.title
    margin-top:.2rem
    line-height:.8rem
    background:#eee
    text-indent:.2rem
.item
    display:flex
    height:1.9rem
    overflow:hidden
.border-bottom
    border-bottom: .01rem solid #eaeaea
    .item-img
        width:1.7rem
        height:1.7rem
        padding:.1rem
    .item-info
        flex:1
        padding:.1rem
        min-width:0
        .item-title
            line-height:.54rem
            font-size:.32rem
            ellipsis()
        .item-desc
            line-height:.4rem
            color:#ccc
            ellipsis()
        .item-btn
            line-height:.44rem
            margin-top:.16rem
            background:#ff9300
            padding:0 .2rem
            border-radius:.06rem
            color:#fff

</style>
      