<template>
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 10px">基本情報登録</h3>
        <div class="st-title_p">
          <p>
            外国式氏名が戸籍に記載されている場合、国際結婚により戸籍上の姓が外国式の姓となっている、もしくは重国籍で戸籍上の氏名が外国式の氏名となっている場合、戸籍上の綴りで入力してください。
          </p>
        </div>
      </div>
      <div class="">
        <div class="info-input" v-for="info in infos" :key="info">
          <div class="st-title_p">
            <p :class="{'p-2':!info.isActive,'p-3':!info.none}"  class="p-1">必須</p>
            <p>{{ info.detail }}</p>
          </div>
           <p style="margin: 5px">{{ info.desc }}</p>
          <!-- INPUT -->
          <div class="input-info">
            <ComponentInput v-if="info.type == 'text'" />
          </div>
          <!-- INPUT -->

          <!-- INPUT-CHECKBOX -->
          <div class="check-info">
            <ComponentCheck v-if="info.type == 'check'" />
          </div>
          <!-- INPUT-CHECKBOX -->

          <!-- INPUT DATE -->
          <div class="date-info">
            <ComponentDate v-if="info.type == 'date'" />
          </div>
          <!-- INPUT DATE -->
        </div>
      </div>
    </div>
</template>

<script>
import ComponentDate from "./ComponentDate.vue";
import ComponentCheck from "./ComponentCheck.vue";
import ComponentInput from "./ComponentInput.vue";

export default {
  components: {
    ComponentInput,
    ComponentCheck,
    ComponentDate,
 
  },
  data() {
    return {
      infos: [
        { title: "", detail: "姓", type: "text",isActive:true ,none:true},
        { title: "", detail: "名", type: "text" ,isActive:true,none:true },
        { title: "", detail: "姓", type: "text" ,isActive:true ,none:true},
        { title: "", detail: "セイ", type: "text" ,isActive:true ,none:true},
        { title: "", detail: "メイ", type: "text",isActive:true ,none:true },
        { title: "", detail: "姓（ローマ字）", type: "text",isActive:true ,none:true },
        { title: "", detail: "性別", type: "check",isActive:true ,none:true },
        { title: "", detail: "生年月日", type: "date",isActive:true ,none:true },
        { title: "", detail: "ビジネスネーム", type: "text" ,desc:"旧姓を利用する等の場合に入力をしてください。",isActive:false ,none:false},
      ],
    }
  }
    
}
  
</script>


<style scoped>

</style>