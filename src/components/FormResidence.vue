<template>
   <div class="st-1">
      <div class="st-title" >
        <h3 style="margin: 0; font-weight: 100">在留カード（外国籍の方はご記入ください）</h3>
      </div>
      <div class="">
        <div class="info-input" v-for="residence in residences" :key="residence">
          <div class="st-title_p" style="display: block">
            <div class="" style="display: flex; margin-right: 0">
              <p :class="{'p-2':!residence.isActive,'p-3':!residence.none}" style="margin-right: 10px" class="p-1">必須</p>
              <p style="font-weight: 700">{{ residence.detail }}</p>
            </div>
            <p style="margin-right: 10px">{{ residence.desc }}</p>
          </div>
            <div class="check-info">
            <ComponentCheckInput v-if="residence.type == 'checkip'" />
          </div>
           <div class="check-info">
            <ComponentInput v-if="residence.type == 'text'" />
          </div>
          <div class="check-info">
            <ComponentDrop v-if="residence.type == 'drop'" />
          </div>
           <div class="check-info">
         <ComponentDateTime v-if="residence.type == 'date'"/>
         </div>

          <div class="check-info">
         <ComponentUpload v-if="residence.type == 'upload'"/>
         </div>


        </div>
      </div>
    </div>
</template>

<script>
import ComponentUpload from "./ComponentUpload.vue";
import ComponentDateTime from "./ComponentCheck.vue";
import ComponentInput from "./ComponentInput.vue";
import ComponentDrop from "./ComponentDrop.vue";
import ComponentCheckInput from "./ComponentCheckInput.vue";

export default {
  components: {
      ComponentCheckInput,
      ComponentDrop,
    ComponentInput,
    ComponentDateTime,
    ComponentUpload,
 
  },
  data() {
    return {
      residences:[
         {
          title: "",
          type: "checkip",
          isActive:true ,none:false
        },
        {
          title: "",
          detail: "姓（ローマ字）",
          type: "text",
            isActive:false ,none:true
        },
        {
          title: "",
          detail: "名（ローマ字）",

          type: "text",
           isActive:false ,none:true
        },
        {
          title: "",
          detail: "姓（カナ）",
          type: "text",
           isActive:false ,none:true
        },
         {
          title: "",
          detail: "名（カナ）",
          type: "text",
           isActive:false ,none:true
        },
         {
          title: "",
          detail: "名（カナ）",
          type: "text",
           isActive:false ,none:true
        },
         {
          title: "",
          detail: "国籍",
          type: "drop",
           isActive:false ,none:true
        },
         {
          title: "",
          detail: "在留資格",
          type: "drop",
           isActive:true ,none:false
        },
         {
          title: "",
          detail: "在留期間（満了日）",
          type: "date",
       isActive:true ,none:false
        },
        {
          title: "",
          detail: "資格外活動許選択してください",
          type: "drop",
            isActive:true ,none:false
        },
         {
          title: "",
          detail: "就労区分",
          type: "drop",
            isActive:true ,none:false
        },
         {
          title: "",
          detail: "在留カード番号（半角）",
          type: "text",
            isActive:false ,none:true
        },
        {
          title: "",
          detail: "在留カードの写真（表）",
          desc:"カードの表の写真を添付してください。",
          type: "upload",
            isActive:true ,none:false
        },
         {
          title: "",
          detail: "在留カードの写真（裏）",
          desc:"カードの裏の写真を添付してください。",
          type: "upload",isActive:true ,none:false
        },
      ],
    }
  }
    
}
  
</script>


<style scoped>

</style>