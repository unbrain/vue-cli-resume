<template>
  <div id="app">
    <Topbar/>
    <main>
      <Editarea/>
      <Preview/>
    </main>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Editarea from './components/Editarea'
import Preview from './components/Preview'

export default {
  name: 'App',
  components: {
    Topbar,
    Editarea,
    Preview
  }
}
</script>

<style lang="scss">
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
  > main {
    display: flex;
    flex: 1;
    justify-content: center;
    margin: 16px;
    
    > div {
      box-shadow: 0px 0px 20px -4px rgba(0, 0, 0, 0.25);
      margin-left: 16px;
      border-radius: 5px;
      overflow: hidden;
    }
  }
}
</style>
