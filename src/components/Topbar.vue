<template>
  <div id="Topbar">
      <p>
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-cv"></use>
        </svg>  
      <p>
      <div>
        <el-button type="primary" plain>注册</el-button>
        <el-button type="success" plain>登录</el-button>
      </div>
  </div>
</template>

<script>
</script>

<style lang="scss">
#Topbar {
  font-size: 14px;
  display: flex;
  justify-content: space-between;
  box-shadow: 0px 5px 20px -4px rgba(0, 0, 0, 0.75);
  z-index: 1;
  > div {
    padding: 16px;
  }
  > p {
    padding: 16px 32px;
    font-size: 32px;
  }
}
</style>
