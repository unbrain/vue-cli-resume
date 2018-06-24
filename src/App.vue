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
import Editare from './components/Editarea'
import Preview from './components/Preview'

export default {
  name: 'App',
  components: {
    Topbar,
    Editare,
    Preview
  }
}
</script>

<style>
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;

}
</style>
