<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img"><img class="icon-img-content" :src="item.imgUrl" /></div>            
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>            
        </swiper>
    </div>
</template>
    
<script>
export default {
    name: 'HomeIcons',
    data () {
        return {
            iconList:[
                {id:'0001',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'景点门票'},
                {id:'0002',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'滑雪季'},
                {id:'0003',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'泡温泉'},
                {id:'0004',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'动植物园'},
                {id:'0005',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'海洋世界'},
                {id:'0006',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'一日游'},
                {id:'0007',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'必游榜单'},
                {id:'0008',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'自然风光'},
                {id:'0009',imgUrl:'https://cdn.pixabay.com/photo/2019/11/25/06/21/leaf-4651088_960_720.jpg',desc:'全部'},
            ]
        }
    },
    computed:{
        pages () {
            const pages=[]
            this.iconList.forEach((item,index) => {
                const page=Math.floor(index / 8)
                if(!pages[page]){
                    pages[page]=[]
                }
                pages[page].push(item)
            })
            return pages;
        }
    }
}
</script>
    
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';
.icons >>> .swiper-container
    height:0
    padding-bottom:50%
.icons
    margin-top:.1rem
    .icon
        position:relative
        overflow:hidden
        width:25%
        height:0
        float:left
        padding-bottom:25%
        .icon-img
            position:absolute
            top:0
            left:0
            right:0
            bottom:.44rem
            box-sizing:border-box
            padding:.1rem
            .icon-img-content
                height:100%
                display:block
                margin:0 auto
        .icon-desc
            position:absolute
            left:0
            right:0
            bottom:0
            line-height:.44rem
            height:.44rem
            color:$dark_text_color
            text-align:center
            ellipsis()
</style>
      