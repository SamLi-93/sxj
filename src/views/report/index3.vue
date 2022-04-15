<template>
  <div class="report-container3">
    <div class="title">报名表</div>
    <div class="upload-box">
      <van-uploader upload-icon="plus" v-model="fileList" :max-size="5000 * 1024" @oversize="onOversize"></van-uploader>
    </div>
    <div class="form-box">
      <van-form @submit="onSubmit">
        <van-field required readonly clickable name="picker" :value="form.examinationVillage" label="报考村社"
                   placeholder="请选择报考村社"
                   @click="showPicker = true"/>
        <van-popup v-model="showPicker" position="bottom">
          <van-picker show-toolbar :columns="columns" @confirm="onConfirm" @cancel="showPicker = false"/>
        </van-popup>
        <van-field required v-model="form.realname" name="姓名" label="姓名" placeholder="请输入姓名"
                   :rules="[{ required: true, message: '请填写姓名' }]"/>
        <van-field required v-model="form.idNum" name="身份证号码" label="身份证号码" placeholder="请输入身份证号码"
                   :rules="[{ required: true, message: '请填写身份证号码' }]"/>
        <van-field required name="uploader" label="请上传身份证正反面照片">
          <template #input>
            <van-uploader v-model="form.idCardPicList" multiple :max-count="2"/>
          </template>
        </van-field>
        <van-field required readonly clickable name="picker" :value="form. partyMember" label="政治面貌"
                   placeholder="请选择政治面貌"
                   @click="showPopup.party = true"/>
        <van-popup v-model="showPopup.party" position="bottom">
          <van-picker show-toolbar :columns="selectListObj.partyList" @confirm="onConfirm"
                      @cancel="showPopup.party = false"/>
        </van-popup>
        <van-field required readonly clickable name="picker" :value="form.educationCertification" label="学历"
                   placeholder="请选择学历"
                   @click="showPopup.party = true"/>
        <van-popup v-model="showPopup.party" position="bottom">
          <van-picker show-toolbar :columns="selectListObj.partyList" @confirm="onConfirm"
                      @cancel="showPopup.party = false"/>
        </van-popup>

        <van-field required readonly clickable name="picker" :value="form.domicile" label="户籍" placeholder="请选择户籍"
                   @click="showPopup.party = true"/>
        <van-popup v-model="showPopup.party" position="bottom">
          <van-picker show-toolbar :columns="selectListObj.partyList" @confirm="onConfirm"
                      @cancel="showPopup.party = false"/>
        </van-popup>

        <van-field required name="isPartyRecommend" label="是否组织推荐">
          <template #input>
            <van-switch v-model="form.isPartyRecommend" size="20"/>
          </template>
        </van-field>
        <van-field required v-model="form.healthStatus" name="健康状况" label="健康状况" placeholder="请输入健康状况"
                   :rules="[{ required: true, message: '请填写健康状况' }]"/>
        <van-field required v-model="form.nowInstitutions" name="现工作（学习）单位" label="现工作（学习）单位" placeholder="请输入现工作（学习）单位"
                   :rules="[{ required: true, message: '请填写现工作（学习）单位' }]"/>
        <van-field required v-model="form.phone" name="联系电话" label="联系电话" placeholder="请输入联系电话"
                   :rules="[{ required: true, message: '请填写联系电话' }]"/>
        <div class="split-line"></div>
        <div>学习简历 从高中开始填写</div>


        <div style="margin: 16px;">
          <van-button round block type="info" native-type="submit">提交</van-button>
        </div>
      </van-form>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      checked: false,
      fileList: [],
      form: {
        realname: '',
        examinationVillage: '',
        idNum: '',
        idCardPicList: [],
        partyMember: '',
        educationCertification: '',
        domicile: '',
        isPartyRecommend: false,
        healthStatus: '',
        nowInstitutions: '',
        phone: '',

      },
      columns: ['杭州', '宁波', '温州', '嘉兴', '湖州'],
      selectListObj: {
        partyList: ['党员', '少数党派', '团员', '群众'],
      },
      showPicker: false,
      showPopup: {
        party: false,
      },
    }
  },
  methods: {
    onConfirm(value) {
      this.value = value;
      this.showPicker = false;
    },
    onSubmit() {

    },
    onOversize(file) {
      console.log(file);
    },
    afterRead() {

    },
    onRead() {

    },
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

  .upload-box {
    margin-top: 20px;
    text-align: center;
  }

  .form-box {
    .split-line {
      height: 5px;
      background-color: rgb(241, 241, 241);
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
