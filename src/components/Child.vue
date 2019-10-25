<template>
    <div id="container">
        {{msg}}
    </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  props:{
    msg: String
  }
};
</script>
<style scoped>
#container{
    color: red;
    margin-top: 50px;
}
</style>
