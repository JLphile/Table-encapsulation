<script setup>
import ATable from "../components/table/ATable.vue"

const column = [
  // {
  //   label: "日期",
  //   prop: "date", //注意不是data,而是date
  //   width: 300,
  // },

  // 通过函数可以用来处理数据
  // {
  //   type: "function",
  //   label: "URL地址",
  //   prop: "date",
  //   callback: (data) => {
  //     // console.log(data)
  //     return `<a href='https://www.bilibili.com'>${data.name}</a>`
  //   },
  // },
  { label: "名称", prop: "name" },
  // { label: "地址", prop: "address" },
  { label: "性别", prop: "gender" },

  // 通过插槽可以引用不同组件标签
  {
    type: "slot",
    label: "操作",
    prop: "operation",
    slot_name: "operation",
  },
]

const jump = (data) => {
  console.log(data)
  
}

</script>

<template>
  <ATable :column="column" checkbox index>
    <template v-slot:operation="slot">
      <!-- {{slot.data.id}} -->
      <el-button type="primary" @click="jump(slot.data)">编辑</el-button>
      <el-button type="primary">删除</el-button>
    </template>
  </ATable>
</template>
