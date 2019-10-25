<template>
  <div id="register">
     <el-form ref="form" :model="form" label-width="100px">

       <el-form-item label="用户名">
         <el-input v-model="form.uname"></el-input>
       </el-form-item>

     <el-form-item label="密码">
       <el-input v-model="form.upwd"></el-input>
     </el-form-item>

     <el-form-item label="确认密码">
       <el-input v-model="form.npwd"></el-input>
     </el-form-item>

    <el-form-item label="邮箱">
       <el-input v-model="form.email"></el-input>
     </el-form-item>

     <el-form-item label="电话">
       <el-input v-model="form.phone"></el-input>
     </el-form-item>

     <el-form-item label="真实姓名">
       <el-input v-model="form.user_name"></el-input>
     </el-form-item>

     <el-form-item label="性别">
       <el-radio-group v-model="form.gender">
         <el-radio label="男"></el-radio>
         <el-radio label="女"></el-radio>
       </el-radio-group>
     </el-form-item>
     <el-form-item>
      <el-button type="primary" @click="onSubmit">注册</el-button>
       <el-button>取消</el-button>
     </el-form-item>
     </el-form>
   </div>
</template>
<script>
export default {
  data(){
    return{
      form:{
        uname:"",
        upwd:"",
        npwd:"",
        email:"",
        phone:"",
        user_name:"",
        gender:""
      }
    }
  },
   methods: {
      onSubmit() {
        console.log('submit!');
      }
    }
}
</script>
<style scoped>
 #register{
   width: 40%;
   display: flex;
   justify-content: center;

 }
</style>