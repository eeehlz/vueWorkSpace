<template>
<div>
  <button v-on:click="addData">+</button>
  <input type="number" v-model.lazy="no">
  <table>
    <thead>
      <tr>
        <th>제품명</th>
        <th>가격</th>
        <th>카테고리</th>
        <th>배송료</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(prod, index) in products"
      v-bind:key="prod.product_no">
        <td>{{ prod.product_no }}</td>
        <td>{{ prod.product_name }}</td>
        <td>{{ prod.price }}</td>
        <td>{{ prod.category }}</td>
        <td>{{ prod.dlivery_price }}</td>
      </tr>
    </tbody>
  </table>
</div>
</template>
<script>
let data = [
  {
    product_no: 1000,
    product_name: "기계식 키보드",
    price: 25000,
    category: "노트북/태블릿",
    dlivery_price: 5000,
  },
  {
    product_no: 2000,
    product_name: "기계식 키보드",
    price: 25000,
    category: "노트북/태블릿",
    dlivery_price: 5000,
  },
  {
    product_no: 3000,
    product_name: "기계식 키보드",
    price: 25000,
    category: "노트북/태블릿",
    dlivery_price: 5000,
  },
  
];

export default {
  data(){
    return{
      products : data,
      no : '',
    }
  },
  methods : {
    addData(event){
      let obj = {
      product_no: ((this.products.length + 1) * 1000),
      product_name: "아이폰",
      price: 15000,
      category: "노트북/태블릿",
      dlivery_price: 5000,
      }
      this.products.push(obj);
    }
  },
  watch :{
    no(){
      this.products.splice(this.no,1);
    }
  }
}
</script>
<style>
table{
    font-family: Arial, Helvetica, sans-serif;
    border-collapse: collapse;
    width : 100%
  }
  td, th{
    border : 1px solid #dddddd;
    text-align: left;
    padding: 8px;
  }
</style>