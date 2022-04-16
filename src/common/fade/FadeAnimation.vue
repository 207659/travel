<template>
    <transition>
        <slot></slot>
    </transition>
</template>
  
<script>
export default {
    name: 'FadeAnimation',
    props: {
        imgs: {
            type: Array,
            default () {
                
            }
        }
    },
    data () {
        return {
            
        }
    },
    methods: {
        
    }
}
</script>
  
<style lang="stylus" scoped>
.v-enter, .v-leave-to
    opacity: 0
.v-enter-active, .v-leave-active
    transition: opacity .5s
</style>
  