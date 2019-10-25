<template>
  <div class="home">
    <myheader :imgurl="url"></myheader>
  </div>
</template>

<script>
// @ is an alias to /src
import MyHeader from '@/components/MyHeader.vue'

export default {
  name: 'home',
  data(){
    return{
      url:""
    }
  },
  components: {
    "myheader":MyHeader
  },
  mounted(){
    var url = "http://localhost:4000/picture"
     this.axios.get(url,{params:{pic_id:2}}).then(result=>{
      this.url=result.data[0].sm;
    })
  }
}
</script>
