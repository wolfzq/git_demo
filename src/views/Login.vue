<template>
  <div id="login">
    <el-form label-width="100px" class="demo-ruleForm" ref="ruleForm">
      <el-form-item label="用户名" prop="uname">
      <el-input v-model="ruleForm.uname" type="text" autocomplete="off" placeholder="请输入密码"></el-input>
      </el-form-item>
    <el-form-item label="密码" prop="pass">
      <el-input v-model="ruleForm.pass" type="password" autocomplete="off" placeholder="请输入密码" show-password></el-input>
      </el-form-item>

  <el-form-item label="确认密码" prop="checkPass">
      <el-input v-model="ruleForm.checkPass" type="password" autocomplete="off" placeholder="请输入密码" show-password></el-input>
      </el-form-item>

  <el-form-item>
    <el-button type="primary" @click="login()">提交</el-button>
    <el-button @click="resetForm()">重置</el-button>
  </el-form-item>
</el-form>
  </div>
</template>
<script>
export default {
  name:"Login",
  data(){
    return{
      ruleForm:{
        pass: '',
        checkPass:'',
        uname:''
      }
    }
  },
  methods:{
    resetForm () {
      this.ruleForm = [];
    },
    login(){
      var u = this.ruleForm.uname;
      var p = this.ruleForm.pass;
      var reg = /^[a-z0-9]{3,12}$/;
      if(reg.test(u)==false){
        this.$message("用户名格式不正确");
        return;
      }
      if(reg.test(p)==false){
        this.$message("密码格式不正确");
        return;
      }
      //发送ajax请求
      var url = "http://localhost:4000/login";
      var obj = {uname:u,upwd:p};
    this.axios.get(url,{params:obj})
    .then(res=>{
      if(res.data.code<0){
        this.$message('用户名或密码有误');
      }else{
        this.$router.push("/");
      }
    })
    }
  },

}   
</script>
<style scoped>
  #login{
    display: flex;
    justify-content: center;
    width: 50%;
  }
</style>