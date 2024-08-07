<script setup>
import { ref } from 'vue'

//宣告一個陣列，該陣列中包含了多個物件，每個物件代表一筆資料，每筆資料有四個屬性，分別是品項、描述、價格、庫存
const rows = ref([
  { id: 1, item: '珍珠奶茶', description: '香濃奶茶搭配QQ珍珠', price: 50, stock: 20 },
  { id: 2, item: '冬瓜檸檬', description: '清新冬瓜配上新鮮檸檬', price: 45, stock: 18 },
  { id: 3, item: '翡翠檸檬', description: '綠茶與檸檬的完美結合', price: 55, stock: 34 },
  { id: 4, item: '四季春茶', description: '香醇四季春茶，回甘無比', price: 45, stock: 10 },
  { id: 5, item: '阿薩姆奶茶', description: '阿薩姆紅茶搭配香醇鮮奶', price: 50, stock: 25 },
  { id: 6, item: '檸檬冰茶', description: '檸檬與冰茶的清新組合', price: 45, stock: 20 },
  { id: 7, item: '芒果綠茶', description: '芒果與綠茶的獨特風味', price: 55, stock: 18 },
  { id: 8, item: '抹茶拿鐵', description: '抹茶與鮮奶的絕配', price: 60, stock: 20 }
])

const addNumber = (row) => {
  row.stock++
}

const minusNumber = (row) => {
  row.stock--
}
</script>

<template>
  <div>
    <h1>六角學院 2024 Vue 前端新手營</h1>
    <br />
    <h2>Week1 作業</h2>
    <br />
    <hr />
    <table>
      <thead>
        <tr>
          <th scope="col">Id</th>
          <th scope="col">品項</th>
          <th scope="col">描述</th>
          <th scope="col">價格</th>
          <th scope="col">庫存</th>
        </tr>
      </thead>
      <!-- 使用v-for指令，將RowDatas陣列中的每一筆資料，透過v-for指令，將資料顯示在表格中 -->
      <tbody>
        <tr v-for="row in rows" :key="row.id">
          <td>{{ row.id }}</td>
          <td>{{ row.item }}</td>
          <td>{{ row.description }}</td>
          <td>{{ row.price }}</td>
          <!-- 數字的加減可以直接引響 stock 數量 -->
          <button @click="minusNumber(row)">-</button>
          <td>{{ row.stock }}</td>
          <button @click="addNumber(row)">+</button>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style></style>

<style scoped></style>
