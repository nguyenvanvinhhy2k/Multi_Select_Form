<template>
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 0; font-weight: 100">保険年金</h3>
      </div>

      <div class="">
        <div class="info-input" v-for="pension in pensions" :key="pension">
          <div class="st-title_p" style="display: block">
            <div class="" style="display: flex">
              <p :class="{'p-2':!pension.isActive,'p-3':!pension.none}"  class="p-1" v-if="pension.isReq">必須</p>

              <p style="font-weight: 700;margin-bottom  : 5px;">{{ pension.detail }}</p>
            </div>
            <p style="margin-top: 0">{{ pension.desc }}</p>
          </div>
          <div class="check-info">
            <ComponentInput v-if="pension.type == 'text'" />
          </div>

          <div class="check-info">
            <ComponentUpload v-if="pension.type == 'upload'" />
          </div>

          <div class="check-info">
            <ComponentCheck v-if="pension.type == 'check'" />
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import ComponentUpload from "./ComponentUpload.vue";
import ComponentCheck from "./ComponentCheck.vue";
import ComponentInput from "./ComponentInput.vue";

export default {
  components: {
    ComponentInput,
    ComponentCheck,
    ComponentUpload,
 
  },
  data() {
    return {
      pensions: [
        { title: "", detail: "基礎年金番号", isReq: true, type: "text" ,isActive:true ,none:true},
        {
          title: "",
          detail: "雇用保険被保険者番号",
          desc: "番号をお持ちの方は必ず入力してください",
          type: "text"
          ,isActive:true ,none:false
        },
        {
          title: "",
          detail: "前職会社名",
          desc: "雇用保険番号が不明の場合は入力をしてください",
          type: "text",isActive:true ,none:false
        },
        {
          title: "",
          detail: "資格証明書類（年金手帳",
          desc: "年金手帳の写真を添付してください",
          type: "upload",isActive:true ,none:false
        },
        {
          title: "",
          detail: "資格署名書類（雇用保険被保険者証",
          desc: "雇用保険被保険者証の写真を添付してください",
          type: "upload",isActive:true ,none:false
        },
        { title: "", detail: "確定拠出年金の利用希望", type: "check" ,isActive:true ,none:false},
      ],
    }
  }
    
}
  
</script>


<style scoped>

</style>