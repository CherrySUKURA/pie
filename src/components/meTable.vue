<template>
  <el-table :data="tableData" style="width: 100%">
    <el-table-column prop="name" label="日期" width="180"></el-table-column>
    <el-table-column prop="value" label="姓名" width="180"></el-table-column>
  </el-table>
</template>
<script>
export default {
  props: {
    tableData: {
      type: Array
    }
  }
};
</script>
