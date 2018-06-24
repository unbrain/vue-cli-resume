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
              <el-input v-model="idcard.name"></el-input>
            </el-form-item>
            <el-form-item label="性别">
              <el-input v-model="idcard.gender"></el-input>
            </el-form-item>
            <el-form-item label="年龄">
              <el-input v-model="idcard.age"></el-input>
            </el-form-item>
          </el-form>
        </li>
        <li :class="{active:currTab === 1}">
          <h1>工作经历</h1>
          <el-form v-for="(company, index) in companys" :key="company.id">
            <div>
              <svg class="icon" aria-hidden="true" @click="removeCompany(index)">
                <use xlink:href="#icon-remove"></use>
              </svg>
            </div>
            <el-form-item label="公司名">
              <el-input v-model="company.name"></el-input>
            </el-form-item>
            <el-form-item label="主要经历">
              <el-input v-model="company.experience"></el-input>
            </el-form-item>
            <hr>
          </el-form>
          <svg class="icon add" aria-hidden="true" @click="addCompany()">
            <use xlink:href="#icon-add"></use>
          </svg>
        </li>
        <li :class="{active:currTab === 2}">
          <h1>学习经历</h1>
          <el-form v-for="school,index in schools" :key="school.id">
            <div>
              <svg class="icon" aria-hidden="true" @click="removeSchool(index)">
                <use xlink:href="#icon-remove"></use>
              </svg>
            </div>
            <el-form-item label="学校名">
              <el-input v-model="school.name"></el-input>
            </el-form-item>
            <el-form-item label="主要经历">
              <el-input v-model="school.experience"></el-input>
            </el-form-item>
            <hr>
          </el-form>
          <svg class="icon add" aria-hidden="true" @click="addSchool()">
            <use xlink:href="#icon-add"></use>
          </svg>
        </li>
        <li :class="{active:currTab === 3}">
          <h1>项目经历</h1>
          <el-form v-for="(work, index) in works" :key="work.id">
            <div>
              <svg class="icon" aria-hidden="true" @click="removeWork(index)">
                <use xlink:href="#icon-remove"></use>
              </svg>
            </div>
            <el-form-item label="项目名">
              <el-input v-model="work.name"></el-input>
            </el-form-item>
            <el-form-item label="技术栈">
              <el-input v-model="work.skills"></el-input>
            </el-form-item>
            <el-form-item label="项目描述">
              <el-input v-model="work.description"></el-input>
            </el-form-item>
            <hr>
          </el-form>
          <svg class="icon add" aria-hidden="true" @click="addWork()">
            <use xlink:href="#icon-add"></use>
          </svg>
        </li>
        <li :class="{active:currTab === 4}">
          <h1>获奖情况</h1>
          <el-form v-for="honor,index in honors" :key="honor.id">
            <div>
              <svg class="icon" aria-hidden="true" @click="removeHonor(index)">
                <use xlink:href="#icon-remove"></use>
              </svg>
            </div>
            <el-form-item label="时间">
              <el-input v-model="honor.year"></el-input>
            </el-form-item>
            <el-form-item label="奖项名字">
              <el-input v-model="honor.name"></el-input>
            </el-form-item>
            <hr>
          </el-form>
          <svg class="icon add" aria-hidden="true" @click="addHonor()">
            <use xlink:href="#icon-add"></use>
          </svg>
        </li>
        <li :class="{active:currTab === 5}">
          <h1>联系方式</h1>
          <el-form v-for="phone,index in phones" :key="phone.id">
            <div>
              <svg class="icon" aria-hidden="true" @click="removePhone(index)">
                <use xlink:href="#icon-remove"></use>
              </svg>

            </div>
            <el-tag>方式{{index+1}}</el-tag>
            <el-input v-model="phone.name"></el-input>
            <el-input v-model="phone.number"></el-input>

            <hr>
          </el-form>
          <svg class="icon add" aria-hidden="true" @click="addPhone()">
            <use xlink:href="#icon-add"></use>
          </svg>
        </li>
      </ol>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currTab: 0,
      icons: ['idcard', 'company', 'books', 'works', 'honor', 'phone'],
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
  },
  methods: {
    addCompany() {
      this.companys.push({ name: '', experience: '' })
    },
    removeCompany(index) {
      this.companys.splice(index, 1)
    },
    addSchool() {
      this.schools.push({ name: '', experience: '' })
    },
    removeSchool(index) {
      this.schools.splice(index, 1)
    },
    addWork() {
      this.works.push({ name: '', skills: '', description: '' })
    },
    removeWork(index) {
      this.works.splice(index, 1)
    },
    addHonor() {
      this.honors.push({ name: '', year: '' })
    },
    removeHonor(index) {
      this.honors.splice(index, 1)
    },
    addPhone() {
      this.phones.push({ name: '手机', number: '' })
    },
    removePhone(index) {
      this.phones.splice(index, 1)
    }
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
          bottom: -8px;
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
    .add {
      right: 24px;
      bottom: -4px;
    }
  }
}
</style>
