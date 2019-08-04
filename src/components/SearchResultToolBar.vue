<template>
  <div class="search-result-toolbar">
    <RoundSearchBar :search="search"/>
  </div>
</template>
<script>
import RoundSearchBar from "@/components/RoundSearchBar.vue"
export default {
    name:"search-result-toolbar",
    components:{RoundSearchBar},
    props:['search']

}
</script>
<style lang="less" scoped>
.search-result-toolbar{
  padding-bottom: 20px;
  border-bottom: 1px #ccc solid
}
</style>
