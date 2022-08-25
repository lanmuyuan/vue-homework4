<template>
  <div>
    <span>欢迎光临_vue开发的收银系统</span>
    <table border="1">
      <thead>
        <th>苹果10￥/斤，折扣8折</th>
      </thead>
      <tbody>
        <tr>
          <td>请输入你要购买的斤数<input type="number" v-model.number="axe"></td>
        </tr>
        <tr>
          <td><button @click="invoicing">结账买单~</button></td>
        </tr>
         <tr>
          <td>结账单：总价{{sum}}￥元 折后价：{{discount}}￥元 省了：{{saveMoney}}￥元</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data(){
    return {
      axe:'',
      sum:0,
      discount:0,
      saveMoney:0
    }
  },
  methods:{
    invoicing(){
      this.sum=this.axe*10
      this.discount=this.sum*0.8
      this.saveMoney=this.sum-this.discount
    }
  }
}
</script>

<style>

</style>
