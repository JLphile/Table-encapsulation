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
        >
          <template #default="scope">
            <div v-html="item.callback && item.callback(scope.row)"></div>
          </template>
        </el-table-column>

        <el-table-column
          v-if="item.type === 'slot'"
          :key="item.prop"
          :prop="item.prop"
          :label="item.label"
          :width="item.width"
        >
          <template #default="scope">
            <slot :name="item.slot_name" :data="scope.row" />
          </template>
        </el-table-column>

        <el-table-column v-else :prop="item.prop" :label="item.label" :width="item.width"></el-table-column>
      </template>
    </el-table>
  </div>
</template>

<script setup>
const tableData = [
  {
    date: "2016-05-03",
    name: "Bilibili",
    address: "No. 189, Grove St, Los Angeles",
    gender: "男",
    id: 1,
  },
  {
    date: "2016-05-02",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
    gender: "女",
    id: 2,
  },
  {
    date: "2016-05-04",
    name: "Lily",
    address: "No. 189, Grove St, Los Angeles",
    gender: "女",
    id: 3,
  },
  {
    date: "2016-05-01",
    name: "Jack",
    address: "No. 189, Grove St, Los Angeles",
    gender: "男",
    id: 4,
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
