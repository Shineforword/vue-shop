<template>
  <div class="home">
    <el-button type="info" @click="logoutAction">退出</el-button>
  </div>
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

<style scoped></style>
