<template>
    <div style="position: relative;">
        <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
        <detail-header></detail-header>
        <div class="content">
            <detail-list :list="list"></detail-list>
        </div>
    </div>
</template>
  
<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
    name: 'detail',
    components: {
        DetailBanner,DetailHeader,DetailList
    },
    data () {
        return {
            sightName: '',
            bannerImg: '',
            gallaryImgs: [],
            list:[
                {title:'成人票',
                    children:[{title:'成人三馆联票',
                        children:[{title:'成人三馆-某一连锁店销售'}]},
                        {title:'成人五馆联票'}]
                },
                {title:'学生票'},
                {title:'儿童票'},
                {title:'特惠票'}
            ]
        }
    },
    methods:{
        getDetailInfo () {
            axios.get('/api/detail.json', {
                params: {
                    id: this.$route.params.id
                }
            }).then(this.handleGetDataOK)
        },
        handleGetDataOK (res) {
            res = res.data
            if (res.ret && res.data) {
                const data = res.data
                this.sightName = data.sightName
                this.bannerImg = data.bannerImg
                this.gallaryImgs = data.gallaryImgs
                this.list = data.categoryList
            }
        }
    },
    mounted () {
        this.getDetailInfo()
    }
}
</script>
  
<style lang="stylus" scoped>
.content
    min-height:8rem
</style>
  