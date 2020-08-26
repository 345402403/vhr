<template>
  <div>
    <el-form :rules="rules" ref="loginForm" :model="loginForm" class="logincontainer">
      <h3 class="logintitle">系统登录</h3>
      <el-form-item prop="username">
        <el-input type="text" v-model="loginForm.username" auto-complete="off" placeholder="用户名"></el-input>
      </el-form-item>
      <el-form-item prop="password">
        <el-input type="password" v-model="loginForm.password" auto-complete="off" placeholder="密码"></el-input>
      </el-form-item>
      <el-checkbox v-model="checked" class="loginRemener"></el-checkbox>
      <el-button type="primary" style="width: 100%" @click="submitLogin">登录</el-button>
    </el-form>
  </div>
</template>

<script>
  export default {
    name: "Login",
    data() {
      return {
        checked:true,
        loginForm: {
          username: 'admin',
          password: '123',
        },
        rules: {
          username: [{required: true, message: '请输入用户名', trigger: 'blur'}],
          password: [{required: true, message: '请输入密码', trigger: 'blur'}],
        }
      }
    },
    methods: {
      submitLogin(){
        this.$refs.loginForm.validate((valid) => {
          if(valid){
            alert("t")
          } else {
            this. $message.error('缺少必填项')
          }
        })
      },
    },
  }
</script>

<style>
 .logincontainer {
   border-radius: 15px;
   background-clip: padding-box;
   margin: 180px auto;
   width: 350px;
   padding: 15px 35px 15px 35px;
   background-color: white;
   border: 1px solid #eaeaea;
   box-shadow: 0 0 15px #cac6c6;
 }
  .logintitle{
    margin: 15px auto 15px auto;
    text-align: center;
    color: #505458;
  }
  .loginRemener{
    text-align: left;
    margin: 0 0 15px 0;
  }
</style>
