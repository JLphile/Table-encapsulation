<script setup>
import ATable from "../components/table/ATable.vue"

const column = [
  //   {
  //     label: "日期",
  //     prop: "date", //注意不是data,而是date
  //     width: 300,
  //   },
  {
    type: "function",
    label: "URL地址",
    prop: "date",
    callback: () => {
      return 11
    },
  },
  {
    label: "名称",
    prop: "name",
    width: 300,
  },
  {
    label: "地址",
    prop: "address",
    width: 300,
  },
  {
    label: "性别",
    prop: "sex",
    width: 300,
  },
]
</script>

<template>
  <ATable :column="column" checkbox index></ATable>
</template>
