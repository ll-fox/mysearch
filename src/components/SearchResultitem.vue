<template>
<div class="search-result-item">
    <a :href="info.url" class="search-result-item-link">
        <div class="title">{{info.title}}</div>
        <div class="url">{{info.url}}</div>
        <div class="desc">{{info.date}}-{{info.desc}}</div>
    </a>
</div>
</template>
<script>
export default {
    props:["info"]
}
</script>
<style lang="less" scoped>
.search-result-item{
    // border: 1px #ccc solid;
    text-align: left;
    padding: 20px
}
.title{
    color: #190DAA;
    font-size: 1.25em;
}
.url{
    color: #006620;
    font-weight: bold;
}
.desc{
    color: #545454
}
.search-result-item-link{
    text-decoration: none;
}
</style>

