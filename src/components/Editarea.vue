<template>
  <div id="Editarea">
    <div class="items">
      <ol>
        <li v-for="(item , index) in icons" :class="{active:currTab === index}" @click="currTab = index">
          <svg class="icon" aria-hidden="true">
            <use :xlink:href="`#icon-${icons[index]}`"></use>
          </svg>
        </li>

      </ol>
    </div>
    <div class="contents">
      <ol>
        <li :class="{active:currTab === 0}">
          <h1>身份信息</h1>
          <el-form>
            <el-form-item label="姓名">
              <el-input v-model="resume.idcard.name"></el-input>
            </el-form-item>
            <el-form-item label="性别">
              <el-input v-model="resume.idcard.gender"></el-input>
            </el-form-item>
            <el-form-item label="年龄">
              <el-input v-model="resume.idcard.age"></el-input>
            </el-form-item>
          </el-form>
        </li>
        <li :class="{active:currTab === 1}">
          <edit-arr :items="resume.companys" :title="'工作经历'" :labels="{name:'公司名', experience:'主要经历'}"></edit-arr>
        </li>
        <li :class="{active:currTab === 2}">
          <edit-arr :items="resume.schools" :title="'学习经历'" :labels="{name:'学校名', experience:'主要经历'}"></edit-arr>
        </li>
        <li :class="{active:currTab === 3}">
          <edit-arr :items="resume.works" :title="'项目经历'" :labels="{name:'项目名', skills:'技术栈', description: '项目描述'}"></edit-arr>
        </li>
        <li :class="{active:currTab === 4}">
          <edit-arr :items="resume.honors" :title="'获奖情况'" :labels="{name:'奖项名字', year: '时间'}"></edit-arr>
        </li>
        <li :class="{active:currTab === 5}">
          <h1>联系方式</h1>
          <el-form v-for="phone,index in resume.phones" :key="phone.id">
            <el-tag>方式{{index+1}}</el-tag>
            <el-input v-model="phone.name"></el-input>
            <el-input v-model="phone.number"></el-input>
            <hr>
          </el-form>
        </li>
      </ol>

    </div>
  </div>
</template>

<script>
import EditArr from './EditArr'
export default {
  props:['resume'],
  components: { EditArr },
  data() {
    return {
      currTab: 0,
      icons: ['idcard', 'company', 'books', 'works', 'honor', 'phone'],
      
    }
  },
  methods: {
    // addPhone() {
    //   this.phones.push({ name: '手机', number: '' })
    // },
    // removePhone(index) {
    //   this.phones.splice(index, 1)
    // }
  }
}
</script>

<style lang="scss">
#Editarea {
  display: flex;
  width: 30%;
  .items {
    background: #f0f9eb;
    box-shadow: 3px 0px 28px -6px rgba(0, 0, 0, 0.59);
    li {
      &.active {
        background: #67c23a;
        .icon {
          fill: #ffffff;
        }
      }
      padding: 24px;
      .icon {
        fill: #67c23a;
        width: 2em;
        height: 2em;
      }
    }
  }
  .contents {
    flex: 1;
    padding-right: 16px;
    overflow: auto;
    hr {
      border: 1px solid #eaecef;
    }
    li {
      position: relative;
      display: none;
      padding: 24px;
      &.active {
        display: block;
      }
      div {
        padding: 8px 0;
        position: relative;
        .icon {
          bottom: -16px;
        }
      }
    }
    .icon {
      fill: #67c23a;
      width: 20px;
      height: 20px;
      position: absolute;
      right: 0;
    }
  }
}
</style>
