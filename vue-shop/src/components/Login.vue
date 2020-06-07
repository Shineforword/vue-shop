<template>
  <div class="login_container">
    <div class="login_box">
      <!-- 头像区 -->
      <div class="avatar_box">
        <img src="../assets/logo.png" alt="">
      </div>
      <!-- 登录表单区 -->
      <el-form label-width="0px" class="login_form" :model="loginForm">
         <el-form-item>
             <el-input prefix-icon="iconfont icon-user" v-model="loginForm.userName"></el-input>
        </el-form-item>
        <el-form-item>
             <el-input prefix-icon="iconfont icon-3702mima" v-model="loginForm.password" type="password"></el-input>
        </el-form-item>
        <el-form-item class="login_btns">
          <el-button type="primary" >登录</el-button>
          <el-button type="info" >重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      loginForm: {
        userName: '',
        password: ''
      }
    }
  }
}
</script>

<style scoped>

.login_container {
  background: #2b4b6b;
  height: 100%;
}
.login_box{
  width: 450px;
  height: 300px;
  background-color: #fff;
  border-radius: 3px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
}

.avatar_box{
  height: 130px;
  width: 130px;
  border: solid 1px #eeeeee;
  border-radius: 50%;
  padding: 10px;
  box-shadow: 0 0 10px;
  position: absolute;
  left: 50%;
  transform: translate(-50%,-50%);
  background-color: #fff;
}
.avatar_box img{
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #eeeeee;
}
.login_form{
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 0 20px;
  box-sizing: border-box;
}
.login_btns{
  display: flex;
  justify-content: flex-end;
}

</style>>
