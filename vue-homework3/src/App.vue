<template>
  <div>
    <label v-for="(item, index) in arr" :key="index">
      <input type="checkbox" :value="item" v-model="newArr">{{item}}
    </label><br>
    <span>你选中的元素，累加的值和为：{{sum}}</span>
  </div>
</template>

<script>

export default {
  data() {
    return {
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      newArr: [],
      sum:0
    }
  },
  watch:{
    newArr:{
      deep: true,
      handler(newValue){
       this.sum= newValue.reduce((acc,res)=>{
          return acc+res
        },0)
      }
    }
  }
}
</script>

<style>
</style>
