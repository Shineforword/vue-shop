<template>
  <div class="login_container">
    <div class="login_box">
      <div class="avatar_box">
        <img src="../assets/logo.png" alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {}
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
</style>>
