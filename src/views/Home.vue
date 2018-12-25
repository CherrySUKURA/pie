<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <meEcharts :tableData="tableData" msg="Welcome to Your Vue.js App"/>
    <meTable :tableData="tableData"></meTable>
    <div>
      <meform @divSub="handleSubInput"></meform>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import meEcharts from "@/components/meEcharts.vue";
import meTable from "@/components/meTable.vue";
import meform from "@/components/meform.vue";

export default {
  name: "home",
  components: {
    meEcharts,
    meTable,
    meform
  },
  data() {
    return {
      tableData: [
        { name: "A", value: "20000" },
        { name: "B", value: "11111" },
        { name: "C", value: "20000" },
        { name: "D", value: "20000" }
      ]
    };
  },
  methods: {
    handleSubInput({ index, val }) {
      console.log("zhi", index);
      this.setValue(index, val);
    },
    setValue(index, val) {
      this.tableData.push({
        name: index,
        value: val
      });
    }
  }
};
</script>
