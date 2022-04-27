<template>
  <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 0">保険年金</h3>
        <div class="st-title_p" style="display:block">
        
          <p>最終学歴が大学院の方は、｢+学歴を追加する｣から大学を登録後に大学院を登録してください。</p>
        
        </div>

      </div>

      <div class="">
        <div
          class="info-input"
          v-for="insurance in insurances"
          :key="insurance"
        >
          <div class="st-title_p">
            <p :class="{'p-2':!insurance.isActive,'p-3':!insurance.none}"  class="p-1">必須</p>
            <p style="font-weight:600">{{ insurance.detail }}</p>
          </div>
            <p style="margin-right: 10px">{{ insurance.desc }}</p>
            <div class="input-info">
            <ComponentInput
              v-if="insurance.type == 'text'"
              style="position: relative"
            />
          </div>

               <div class="input-info">
            <componentBox v-if="insurance.type == 'box'" />
          </div>

           <div class="input-info">
            <ComponentCheck v-if="insurance.type == 'check'" />
          </div>

     
        </div>
        <div class="plus" >
          <img
            style="
              width: 18px;
              height: 18px;
              margin-right: 10px;
              margin-left: 5px;
            "
            src="../assets/plus.png"
            alt=""
          />
          <p style="color: #007bc3; font-size: 18px">学歴を追加する</p>
        </div>
      </div>
    </div>
</template>

<script>
import ComponentBox from './ComponentBox.vue';
import ComponentCheck from "./ComponentCheck.vue";
import ComponentInput from "./ComponentInput.vue";



export default {
  components: {
    ComponentInput,
 
    ComponentCheck,
    ComponentBox,
  },
  data() {
    return {
              insurances: [{
                title: "",
                detail: "基礎年金番号",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "雇用保険被保険者番号",
                desc: "番号をお持ちの方は必ず入力してください",
                type: "text",
                none: false,
                isActive: false
            },
            {
                title: "",
                detail: "前職会社名",
                desc: "雇用保険番号が不明の場合は入力をしてください",
                type: "text",
                none: false,
                isActive: false
            },
            {
                title: "",
                detail: "学校名",
                type: "text",
                none: false,
                isActive: true
            },
            {
                title: "",
                detail: "資格証明書類（年金手帳）",
                desc: "年金手帳の写真を添付してください",
                type: "box",
                none: false,
                isActive: false
            },
            {
                title: "",
                detail: "資格署名書類（雇用保険被保険者証）",
                desc: "年金手帳の写真を添付してください",
                type: "box",
                none: false,
                isActive: false
            },
            {
                title: "",
                detail: "確定拠出年金の利用希望",
                type: "check",
                none: false,
                isActive: false
            },
        ]
    }
  }
    
}
  
</script>


<style scoped>

</style>