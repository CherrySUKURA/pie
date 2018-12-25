<template>
  <div style="margin-top: 15px;">
    <el-input placeholder="请输入销量" v-model="select"></el-input>
    <el-input placeholder="请输入销量" v-model="input5"></el-input>
    <el-button slot="append" icon="el-icon-upload" @click="divclick" id="el-button-from">确定</el-button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      input5: "",
      select: ""
    };
  },
  methods: {
    divclick: function() {
      let index = this.select;
      let val = this.input5;
      this.$emit("divSub", { index, val });
    }
  }
};
</script>

