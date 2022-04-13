<template>
  <div class="report-container3">
    <div class="title">报名表</div>



  </div>
</template>

<script>
export default {
  data() {
    return {
      checked: false,
    }
  },
  methods: {
    handleToForm() {
      if (this.checked) {
        this.$router.push(`/login`)
      }
    },
  }
}
</script>

<style scoped lang="less">
.report-container3 {
  padding: 10px;

  .title {
    margin: 0 auto;
    margin-top: 10px;
    width: 200px;
    text-align: center;
    background-color: rgb(36, 88, 224);
    color: #fff;
    border-radius: 5px;
    padding: 20px;
    font-size: 24px;
    font-weight: bold;
  }

  .btn-box {
    button {
      width: 100%;
    }
  }

}
</style>

<style lang="less">
.report-container {
  .el-checkbox__label {
    color: #6a6adb;
    margin-top: 30px;
    margin-bottom: 10px;
  }
}
</style>
