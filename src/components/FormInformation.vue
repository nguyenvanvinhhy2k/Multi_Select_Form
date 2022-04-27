<template>
  <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 0">家族情報を登録</h3>
        <div class="st-title_p" style="display:block">
          <p>一等親以内は同居/別居に関わらず記入</p>
          <p>二親等以上は同居、もしくは扶養義務がある場合に限り記載</p>
        
        </div>
        <p style="margin: 0; font-weight: 900">緊急連絡先1</p>
      </div>

      <div class="">
        <div
          class="info-input"
          v-for="information in informations"
          :key="information"
        >
          <div class="st-title_p">
            <p :class="{'p-2':!information.isActive,'p-3':!information.none}"  class="p-1">必須</p>
            <p>{{ information.detail }}</p>
          </div>
            <p style="margin-right: 10px">{{ information.desc }}</p>
            <div class="input-info">
            <ComponentDrop
              v-if="information.type == 'drop'"
              style="position: relative"
            />
          </div>

               <div class="input-info">
            <ComponentInput v-if="information.type == 'text'" />
          </div>

           <div class="input-info">
            <ComponentCheck v-if="information.type == 'check'" />
          </div>

            <div class="input-info">
            <ComponentDate v-if="information.type == 'date'" />
          </div>


          <div class="input-info">
            <ComponentDateCode v-if="information.type == 'date1'" />
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
import ComponentCheck from "./ComponentCheck.vue";
import ComponentDrop from "./ComponentDrop.vue";
import ComponentInput from "./ComponentInput.vue";
import ComponentDate from "./ComponentDate.vue";
import ComponentDateCode from "./ComponentDateCode.vue";

export default {
  components: {
    ComponentInput,
    ComponentDrop,
    ComponentCheck,
    ComponentDate,
    ComponentDateCode
 
  },
  data() {
    return {
       informations:[
            {
          title: "",
         detail: "続柄",
          type: "drop", none:true,isActive:true 
        },
        {
          title: "",
          detail: "姓",
          type: "text", none:true,isActive:true 
        },
        {
          title: "",
          detail: "名",
          type: "text", none:true,isActive:true 
        },
         {
          title: "",
          detail: "セイ",
        
          type: "text", none:true,isActive:true 
        },
         {
          title: "",
          detail: "メイ",
          type: "text", none:true,isActive:true 
        },
         {
          title: "",
          detail: "姓（ローマ字）",
        
          type: "text", none:true,isActive:true 
        },
         {
          title: "",
          detail: "名（ローマ字）",
          type: "text", none:true,isActive:true 
        },
        {
          title: "",
          detail: "性別",

          type: "check", none:true,isActive:true 
        },
         {
          title: "",
          detail: "生年月日",
          type: "date", none:true,isActive:true 
        },
         {
          title: "",
          detail: "同居/別居",
          desc:"別居を選択すると住所の入力が必須になります",
          type: "check", none:true,isActive:true 
        },
         {
          title: "",
          detail: "郵便番号",
          type: "date1", none:true,isActive:true 
        },
{
          title: "",
          detail: "都道府県",
          type: "text", none:true,isActive:true 
        },
         {
          title: "",
          detail: "市区町村",
 
          type: "text", none:true,isActive:true 
        },
         {
          title: "",
          detail: "番地",
          type: "text", none:true,isActive:true 
        },
         {
          title: "",
          detail: "建物名称・部屋番号",
          type: "text", none:false,isActive:true 
        },
         {
          title: "",
          detail: "勤務先・学校名",
          type: "text", none:false,isActive:true 
        },
         {
          title: "",
          detail: "職業区分",
          type: "drop", none:false,isActive:true 
        },
         {
          title: "",
          detail: "職業区分でその他を選択の理由",
          desc:"その他を選択した方は、詳細内容を入力してください。学生を選択した方は、大学○年生など、具体的に入力をお願いいたします",
          type: "text", none:false,isActive:true 
        },
         {
          title: "",
          detail: "健康保険扶養区分",
          type: "drop", none:false,isActive:true 
        },

        ],
    }
  }
    
}
  
</script>


<style scoped>

</style>