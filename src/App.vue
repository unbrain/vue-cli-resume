<template>
  <div id="app">
    <Topbar/>
    <main>
      <Editarea :resume="resume" />
      <Preview :resume="resume" />
    </main>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Editarea from './components/Editarea'
import Preview from './components/Preview'
import { WiredButton, WiredInput } from 'wired-elements'

export default {
  name: 'App',
  components: {
    Topbar,
    Editarea,
    Preview
  },
  data() {
    return {
      resume: {
        idcard: {
          name: '',
          gender: '',
          age: ''
        },
        companys: [{ name: '', experience: '' }],
        schools: [{ name: '', experience: '' }],
        works: [{ name: '', skills: '', description: '' }],
        honors: [{ name: '', year: '' }],
        phones: [
          { name: '手机', number: '' },
          { name: '微信', number: '' },
          { name: 'E-mail', number: '' },
          { name: 'GitHub', number: '' }
        ]
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
  > main {
    min-width: 1024px;
    max-width: 1440px;
    width: 100%;
    display: flex;
    flex-direction: row;
    margin-top: 16px;
    margin-bottom: 16px;
    flex: 1;
    justify-content: center;
    align-self: center;
    > div {
      box-shadow: 0px 0px 20px -4px rgba(0, 0, 0, 0.25);
      border-radius: 5px;
      overflow: hidden;
    }
  }
}
</style>
