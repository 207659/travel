<template>
    <ul class="list">
        <li class="item" v-for="item of letters" :key="item" :ref="item"
        @touchstart.prevent="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        @click="handleLetterClick">{{item}}</li>
    </ul>
</template>
  
<script>
export default {
    name: 'CityAlphabet',
    props: {
        cities: Object
    },
    computed: {
        letters () {
            const letters=[]
            for(let i in this.cities) {
                letters.push(i)
            }
            return letters
        }
    },
    data () {
        return {
            touchStatus: false,
            srartY:0,
            timer:null
        }
    },
    updated () { //性能优化1
        this.srartY=this.$refs['A'][0].offsetTop
    },
    methods:{
        handleLetterClick (e) {
            // console.log(e.target.innerText)
            this.$emit('change',e.target.innerText)
        },
        handleTouchStart () {
            this.touchStatus=true
        },
        handleTouchMove (e) {
            if (this.touchStatus) {
                if (this.timer) {
                    clearTimeout(this.timer)
                }
                 //性能优化2：函数节流
                this.timer=setTimeout(() => {
                    // const srartY=this.$refs['A'][0].offsetTop
                    const touchY=e.touches[0].clientY-79    //79是A字母顶部到头部下边
                    const index=Math.floor((touchY-this.srartY)/20)  //20是每个字母的高度
                    // console.log(index)
                    if (index >= 0 && index < this.letters.length) {
                        this.$emit('change',this.letters[index])
                    }
                }, 16)
            }
        },
        handleTouchEnd () {
            this.touchStatus=false
        }
    }
}
</script>
  
  <style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .list
    display:flex
    flex-direction:column
    justify-content:center
    position:absolute
    top:1.58rem
    right:0
    bottom:0
    width:.4rem
    .item
        line-height:.4rem
        text-align:center
        color:$bg_color
  </style>
  