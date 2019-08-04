<template>
    <div class="round-search-bar">
        <div @click="goHome">
            <MySearchLogo class="my-search-logo"/>
        </div>
        <input v-model="search" class="input-search" @keydown.enter="doSearch">
        <button class="btn-search" @click="doSearch">
            <i class="icon-search iconfont icon-RectangleCopy"></i>
        </button>
    </div>
</template>
<script>
import Util from "@/common/Util"
import MySearchLogo from "@/components/MySearchLogo.vue"
export default {
    name:"round-search-bar",   
    components:{
        MySearchLogo
    } ,
    props:['search'],
    methods: {
        doSearch(){
            Util.searchAPI(this.$router,this.search)
        },
        goHome(){
            this.$router.push("/")
        }
    },
}
</script>
<style lang="less" scoped>
@import "./../themes/base.less";
.my-search-logo{
    display: flex;
    padding: 0 20px;
}
.round-search-bar{
    display: flex;
    align-items: center;
    width: 800px;
    position: relative;
}
.input-search{
    outline: none;
    font-size: 1.2em;
    width: 100%;
    height: @round-search-bar-height;
    border-radius: @round-search-bar-border-radius;
    border: 1px #ccc solid;
    padding: 20px;
    box-sizing: border-box;
}
.btn-search{
    outline: none;
    height: @round-search-bar-height;
    position: absolute;
    right: 0;
    top:50%;
    transform: translateY(-50%);
    background: none;
    border: none;
    .icon-search{
        font-size: 30px;
        color: @color-border-gray;
        margin-right: 15px;
    }
}
</style>

