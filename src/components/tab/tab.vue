<template>
    <div class="tab border-1px">
        <router-link tag="div" class="tab-item" to="/goods">
            <span class="tab-link"> 商品 </span>
        </router-link>
        <router-link tab="div" class="tab-item" to="/ratings">
            <span class="tab-link"> 评论 </span>
        </router-link>
        <router-link tag="div" class="tab-item" to="/seller">
            <span class="tab-link"> 商家 </span>
        </router-link>
    </div>
</template>

<script>
    export default {

    };
</script>

<style lang="stylus" rel="stylesheet/stylus">
    @import '../../common/stylus/mixin.styl'

    .tab
        display: flex
        height: 44px
        line-height: 44px
        font-size: 14px
        border-1px(rgba(7,17,27,0.1))
        .tab-item
            flex: 1
            text-align: center
            .tab-link
                padding-bottom: 5px
                color: #000
            &.router-link-active
                .tab-link
                    // border-bottom: 2px solid #ffcd32
                    color: #ffcd32
</style>