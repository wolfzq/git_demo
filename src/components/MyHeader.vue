<template>
  <div id="header"> 
    <div id="leftimg">
      <img :src="imgurl" />
    </div>
    <div id="righttext">
      <el-avatar src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png"></el-avatar>
      <router-link to="/Login">登录</router-link> |
      <router-link to="/Register">注册</router-link> |
      <router-link to="/Cart">购物车</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name:"MyHeader",
  data(){
    return{};
  },
  props:{
    imgurl:{default:""}
  }
}
</script>
<style scoped>
#header{
  display: flex;
  justify-content: space-around;
  align-items: center;
}
 #righttext {
  padding: 30px;
}

#righttext a {
  font-weight: bold;
  color: #2c3e50;
}

#righttext a.router-link-exact-active {
  color: #42b983;
}
</style>