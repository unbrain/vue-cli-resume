<template>
  <div id="Topbar">
    <p>
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-cv"></use>
      </svg>
    </p>
    <div>
      <wired-button elevation="3">预览</wired-button>
      <wired-button elevation="3" @click="print()">打印</wired-button>
    </div>
  </div>
</template>

<script>
export default {

  methods: {
    // addPhone() {
    //   this.phones.push({ name: '手机', number: '' })
    // },
    // removePhone(index) {
    //   this.phones.splice(index, 1)
    // }
    print(){
      window.print()
    }
  }
}
</script>

<style lang="scss">
#Topbar {
  font-size: 14px;
  display: flex;
  justify-content: space-between;
  box-shadow: 0px 5px 20px -4px rgba(0, 0, 0, 0.75);
  z-index: 1;
  wired-button {
    fill: white;
    padding: 8px 16px;
    margin: 0 16px;
    &:hover {
      background: #363636;
      color: #ffffff;
      transition: 0.3s;
    }
  }
  > div {
    padding: 16px;
  }
  > p {
    padding: 16px 32px;
    font-size: 32px;
  }
}
</style>
