<template>
  <div id="Preview">

    <div class="contents"></div>
  </div>
</template>

<script>
export default {
  props:['resume'],
  methods: {
    filter(items){
      return items.filter((item) => !this.isEmpty(item))
    },
    isEmpty(obj){
      let empty = true
      for(let key in obj){
        if(obj[key].trim()){
          empty = false
          break
        }
      }
      return empty
    }
  }
}
</script>

<style lang="scss">
#Preview {
  display: flex;
  height: inherit;
  width: 55%;
  margin-left: 16px;
  flex: 1;
}
</style>
