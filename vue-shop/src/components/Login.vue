<template>
  <div class="login_container">
    <div class="login_box">
      <!-- 头像区 -->
      <div class="avatar_box">
        <img src="../assets/logo.png" alt />
      </div>
      <!-- 登录表单区 -->
      <el-form
        label-width="0px"
        class="login_form"
        :model="loginForm"
        :rules="loginFormRules"
        ref="loginFormRef"
      >
        <el-form-item prop="userName">
          <el-input prefix-icon="iconfont icon-user" v-model="loginForm.userName"></el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input
            prefix-icon="iconfont icon-3702mima"
            v-model="loginForm.password"
            type="password"
          ></el-input>
        </el-form-item>
        <el-form-item class="login_btns">
          <el-button type="primary" @click="loginAction">登录</el-button>
          <el-button type="info" @click="resetLoginFormAction">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // 表单数据对象
      loginForm: {
        userName: 'admin',
        password: '123456'
      },
      // 表单验证规则对象
      loginFormRules: {
        //验证用户名是否合法
        userName: [
          { required: true, message: '请输入用户名', trigger: 'blur' },
          { min: 3, max: 10, message: '长度在 3 到 10 个字符', trigger: 'blur' }
        ],
        //验证密码是否合法
        password: [
          { required: true, message: '请输入密码', trigger: 'blur' },
          { min: 6, max: 15, message: '长度在 6 到 15 个字符', trigger: 'blur' }
        ]
      }
    }
  },
  methods: {
    // 点击重置登录表单
    resetLoginFormAction() {
      console.log(this.$refs.loginFormRef)
      //$refs.loginFormRef获取引用对象实例
      this.$refs.loginFormRef.resetFields()
    },
    // 点击登录
    loginAction() {
      // validate函数预校验
      this.$refs.loginFormRef.validate(async valid => {
        console.log(valid)
        if (!valid) return
        // 返回promise对象,添加await ->外部加async
        let loginParams = {
          username: '',
          password: ''
        }
        loginParams.username = this.loginForm.userName
        loginParams.password = this.loginForm.password
        const { data: res } = await this.$http.post('login', loginParams)
        console.log(res)
        if (res.meta.status !== 200) return this.$message.error('登录失败')
        this.$message.success('登录成功')
        /*登录成功保存token到客户端的sessionStore中(回话期间的存储机制)
          项目中除了登录之外的其他api必须在登录之后才能访问
          token只能在当前网站打开期间生效,所以将token保存在sessionStore中
          通过编程式导航跳转到后台主页,路由地址是/home
        */
        window.sessionStorage.setItem('token', res.data.token)
        this.$router.push('/home')
      })
    }
  }
}
</script>

<style scoped>
.login_container {
  background: #f5f5f5;
  height: 100%;
}
.login_box {
  width: 450px;
  height: 300px;
  background-color: #fff;
  border-radius: 3px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.avatar_box {
  height: 130px;
  width: 130px;
  border: solid 1px #eeeeee;
  border-radius: 50%;
  padding: 10px;
  box-shadow: 0 0 10px;
  position: absolute;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #fff;
}
.avatar_box img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #eeeeee;
}
.login_form {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 0 20px;
  box-sizing: border-box;
}
.login_btns {
  display: flex;
  justify-content: flex-end;
}
</style
>>
