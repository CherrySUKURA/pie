<template>
  <div id="main" style="width: 600px;height:400px;"></div>
</template>

<script>
export default {
  props: ["tableData"],
  //在vue渲染到都没元素时启用回调函数
  mounted() {
    this.draw();
  },
  watch: {
    tableData: function() {
      this.draw();
    }
  },
  methods: {
    //指定图表的配置项和数据
    draw() {
      var echarts = require("echarts");
      //导入echar依赖，在node_modules里面，这里说一下import和require的区别，import需要具体到相对地址，而require则不用，会自动安装
      var myChart = echarts.init(document.getElementById("main"));
      myChart.setOption({
        title: {},
        tooltip: {
          trigger: "item",
          formatter: "{a} <br/>{b} : {c} ({d}%)"
        }, //提示框
        series: [
          {
            type: "pie",
            data: this.tableData
          }
        ]
      });
      console.log(this.tableData);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

