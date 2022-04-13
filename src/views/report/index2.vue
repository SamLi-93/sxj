<template>
  <div class="report-container2">
    <div class="title">新埭镇村、社区后备干部</div>
    <div class="title font36">报名系统</div>

    <div class="file-box">
      <div class="file-tip"><i class="el-icon-download"></i>请先下载附件：</div>
      <div class="file-name">新埭镇村、社区后备干部报名表.doc</div>
    </div>


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
.report-container2 {
  padding: 10px;

  .title {
    margin: 0 auto;
    margin-top: 10px;
    text-align: center;
    color: rgb(36, 88, 224);
    padding: 20px;
    font-size: 30px;
    font-weight: bold;
    padding-bottom: 0;
  }

  .font36 {
    font-size: 34px;
    padding: 0;
  }

  .file-box {
    margin: 0 auto;
    margin-top: 50px;
    padding: 10px;
    width: 95%;
    background-color: rgba(246, 246, 246, 0.8);
    .file-tip {
      margin-bottom: 10px;
      font-size: 16px;
      i {
        margin-right: 5px;
      }
    }
    .file-name {
      margin-left: 20px;
      color: rgb(36, 88, 224);
      text-decoration: underline;
    }
  }

}
</style>
