<template>
  <div id="Topbar">
      <p>resume<p>
      <div>
        <button>注册</button>
        <button>登录</button>
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
  box-shadow: 0px 5px 26px -4px rgba(0, 0, 0, 0.75);
  z-index: 1;
  > p,
  div {
    padding: 16px;
  }
}
</style>
