
<template>
    <div id="container">
        <input type="text" v-model="text" @change="dataChange">
        <Child :msg="text"></Child>
    </div>
</template>
<script>
import Child from "@/components/Child";
export default {
  data() {
    return {
      text: "父组件"
    };
  },
  methods: {
    dataChange(data){
        this.msg = data
    }
  },
  components: {
    Child
  }
};
</script>
<style scoped>
</style>
