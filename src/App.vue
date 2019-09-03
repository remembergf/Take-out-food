<template>
    <div id="app">
        <m-header :seller="seller"></m-header>
        <!-- <div class="header">I am header</div> -->
        <tab></tab>
        <keep-alive>
            <router-view :seller="seller"></router-view>
        </keep-alive>
        <!-- <div class="content">
            这是内容区
        </div> -->
    </div>
</template>

<script>

    import MHeader from '@/components/header/header'
    import Tab from '@/components/tab/tab'

    const ERR_OK = 0;

    export default {
        data() {
            return {
                seller: {}
            };
        },
        created() {
            this.$http.get('/api/seller').then((res) => {
                console.log(res);
                res = res.body;
                if(res.errno === ERR_OK) {
                    this.seller = res.data;
                    console.log(this.seller);
                }
            });
        },
        components:{
            MHeader,
            Tab
        }
    };
</script>

<style lang="stylus" rel="stylesheet/stylus">
    #app
        .tab
            display: flex
            width: 100%
            height: 40px;
            line-height: 40px
            .tab-item
                flex: 1
                text-align: center
</style>
