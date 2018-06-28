<template>
  <div id="app" class="clearfix">
    <Topbar/>

    <main>
      <Editarea :resume="resume" :class="{show:editshow,unshow:!editshow}" />

      <Preview :resume="resume" />
    </main>
    <div class="lar">
      <svg class="icon" aria-hidden="true" v-show="editshow" @click="editshow = !editshow">
        <use xlink:href="#icon-left"></use>
      </svg>
      <svg class="icon" aria-hidden="true" v-show="!editshow" @click="editshow = !editshow">
        <use xlink:href="#icon-right"></use>
      </svg>
    </div>

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
      editshow: false,
      resume: {
        idcard: {
          name: 'Bruno Mars',
          gender: 'man',
          age: '22',
          job: 'WEB DEVELOPER'
        },
        companys: [
          {
            job: 'linux developer',
            when: 'April 2018',
            experience: `
            Since 2013, I’ve been colaborating with Nebrija University, giving design talks &
            workshops for graduate students from 2º to 4º course, and master classes for post
            graduate students.`
          }
        ],
        schools: [
          {
            name: 'UC Berkeley',
            professional: 'computer science',
            when: '2015-2018',
            experience:
              ' has worked for major companies in Murcia and has extensive experience in the professional world. He aims to broaden their skills surrounding himself with sector professionals, work with other firms and sharpen their English.'
          }
        ],
        projects: [
          {
            name: 'Momo Painter',
            skills: 'Canvas, JavaScript, CSS3',
            description:
              'My first steps in the digital world, learning to code, to think rationally (I had not yet discovered the creative world) and to create my first apps with the user in mind.'
          },
          {
            name: 'Momo Painter',
            skills: 'Canvas, JavaScript, CSS3',
            description:
              'My first steps in the digital world, learning to code, to think rationally (I had not yet discovered the creative world) and to create my first apps with the user in mind.'
          },
          {
            name: 'Momo Painter',
            skills: 'Canvas, JavaScript, CSS3',
            description:
              'My first steps in the digital world, learning to code, to think rationally (I had not yet discovered the creative world) and to create my first apps with the user in mind.'
          },
          {
            name: 'Momo Painter',
            skills: 'Canvas, JavaScript, CSS3',
            description:
              'My first steps in the digital world, learning to code, to think rationally (I had not yet discovered the creative world) and to create my first apps with the user in mind.'
          },
          {
            name: 'Momo Painter',
            skills: 'Canvas, JavaScript, CSS3',
            description:
              'My first steps in the digital world, learning to code, to think rationally (I had not yet discovered the creative world) and to create my first apps with the user in mind.'
          }
        ],
        honors: [{ name: '', year: '' }],
        phones: [
          { name: 'Phone', number: '183-4911-8888' },
          { name: 'WeChat', number: 'bruno mars' },
          { name: 'E-mail', number: 'brunomars@gmail.com' },
          { name: 'GitHub', number: 'unbrain' }
        ]
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  display: flex;
  flex-direction: column;
  position: relative;


  .show {
    transition: 2s;
    opacity: 0;
    width: 0;
  }
  .unshow {
    transition: 2s;
    opacity: 1;
  }

  > main {
    min-width: 940px;
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
    }
  }
  .lar {
    z-index: 1;
    padding: 8px;
    border-radius: 2px;
    left: 40px;
    top: 84px;
    border: 1px solid #ccc;
    position: absolute;
    .icon {
      width: 40px;
      height: 40px;
      fill: #363636;
    }

      box-shadow: 3px 0px 28px -6px rgba(0, 0, 0, 0.59);
  }
}
</style>
