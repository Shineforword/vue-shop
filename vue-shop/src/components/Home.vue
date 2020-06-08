<template>
  <el-container class="home_container">
    <!-- 头部去 -->
    <el-header>
      <div>
        <img src="../assets/home_logo.png" />
        <span>电商后台管理系统</span>
      </div>
      <el-button type="info" @click="logoutAction">退出</el-button>
    </el-header>
    <!-- 页面主体区 -->
    <el-container>
      <!-- 侧边栏 -->
      <el-aside width="200px">Aside</el-aside>
      <!-- 内容主体 -->
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  methods: {
    logoutAction() {
      window.sessionStorage.clear()
      this.$router.push('login')
    }
  }
}
</script>

<style scoped>
.home_container {
  width: 100%;
  height: 100%;
}
.el-header {
  background-color: #373d41;
  display: flex;
  justify-content: space-between;
  padding-left: 0;
  align-items: center;
  color: #ffffff;
  font-size: 20px;
  font-weight: 700;
}
.el-header div {
  display: flex;
  align-items: center;
}
span {
  margin-left: 15px;
}
.el-aside {
  background-color: #333744;
}
.el-main {
  background-color: #eaedf1;
}
</style>
