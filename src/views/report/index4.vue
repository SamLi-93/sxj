<template>
  <div class="report-container">
    <div class="title">诚信承诺书</div>
    <p>我已仔细阅读新埭镇村、社区后备干部招聘公告，理解并认可其内容。我郑重承诺：</p>
    <p>一、自觉遵守招考有关规定，准确、慎重报考符合条件的职位，并对自己的报名负责。
    <p>二、真实、准确地填写和提供本人的报名信息、证明资料、证件等相关材料，并保证在考试及录用期间联系方式畅通。</p>
    <p>三、认真履行报考人员的各项义务，遵守考试纪律，服从考试安排，不舞弊也不协助他人舞弊。</p>
    <p>四、考后不散布、传播考试试题。不参与言之无据的失实失真言论。</p>
    <p> 五、认同雷同试卷鉴定结果。</p>
    <p>六、不故意浪费考录资源。</p>


    <div>
      <el-checkbox v-model="checked">对违反以上承诺所造成的后果，本人自愿承担相应责任。</el-checkbox>
    </div>
    <div class="btn-box">
      <el-button type="primary" @click="handleToForm">下一步</el-button>
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
.report-container {
  padding: 10px;

  .title {
    margin: 0 auto;
    margin-top: 10px;
    width: 200px;
    text-align: center;
    border: 2px solid rgb(36, 88, 224);
    color: rgb(36, 88, 224);
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
