<template>
  <div class="search-page">
    <SearchResultToolBar :search="search"/>
    <div v-for="info in searchResultList" :key="info.id">
      <SearchResultitem :info="info"/>
    </div>
  </div>
</template>
<script>
import SearchResultToolBar from "@/components/SearchResultToolBar.vue"
import SearchResultitem from "@/components/SearchResultitem.vue"
const DB =require("@/data/search.json")
export default {
  data() {
    return {
      searchResultList:[],
    }
  },
  computed: {
    search(){
      return this.$route.params.searchText
    }
  },
  created() {
    this.doSearchResult()
  },
  beforeRouteUpdate(to,from,next) {
    next()
    this.doSearchResult();
  },
  methods: {
    doSearchResult(){
      const  {searchText}=this.$route.params;
      if(DB.hasOwnProperty(searchText)){
        this.searchResultList=DB[searchText]
      }else{
        this.searchResultList=[]
      }
    }
  },
  components:{
    SearchResultToolBar,
    SearchResultitem
    },
}
</script>
