<template>
  <div>
    <h1>{{title}}</h1>
    {{keys}}
    <el-form v-for="(item, index) in items" :key="index">
      <div>
        <svg class="icon" aria-hidden="true" @click="removeitem(index)">
          <use xlink:href="#icon-remove"></use>
        </svg>
      </div>
      <el-form-item v-for="key,index in keys" :label="labels[key]" :key="key">
        <el-input v-model="item[key]"></el-input>
      </el-form-item>
      <hr>
    </el-form>
    <svg class="icon add" aria-hidden="true" @click="additem()">
      <use xlink:href="#icon-add"></use>
    </svg>
  </div>
</template>

<script>
export default {
  props: ['items', 'title', 'labels'],
  computed:{
    keys(){
      return Object.keys(this.items[0])
    }
  },
  methods: {
    additem(){
      let empty = {}
      this.keys.map(key, ()=>{
        empty[key] = ''
      })
      this.items.push(empty)
    },
    removeitem(index){
      this.items.splice(index, 1)
    }
  },
  data() {
    return {}
  }
}
</script>
