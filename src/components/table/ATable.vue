<template>
  <div>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column v-if="index" type="index" width="40"></el-table-column>
      <el-table-column v-if="checkbox" type="selection" width="40"></el-table-column>
      <template v-for="item in column">
        <el-table-column
          v-if="item.type === 'function'"
          :key="item.prop"
          :prop="item.prop"
          :label="item.label"
          :width="item.width"
        ></el-table-column>
        <el-table-column v-else :prop="item.prop" :label="item.label" :width="item.width"></el-table-column>
      </template>
    </el-table>
  </div>
</template>

<script setup>
const tableData = [
  {
    date: "2016-05-03",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
    sex: "男",
  },
  {
    date: "2016-05-02",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
    sex: "男",
  },
  {
    date: "2016-05-04",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
    sex: "男",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
    sex: "男",
  },
]

const props = defineProps({
  column: {
    type: Array,
    default: () => [],
  },
  checkbox: {
    type: Boolean,
    default: false,
  },
  index: {
    type: Boolean,
    default: false,
  },
})
</script>

<style lang="scss" scoped></style>
