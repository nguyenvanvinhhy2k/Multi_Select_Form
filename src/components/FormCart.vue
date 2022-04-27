<template>
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 10px">在留カード（外国籍の方はご記入ください）</h3>
        <div class="st-title_p">
         
        </div>
      </div>
      <div class="">
        <div class="info-input" v-for="card in cards" :key="card">
          <div class="st-title_p">
            <p :class="{'p-2':!card.isActive,'p-3':!card.none}"  class="p-1">必須</p>
            <p>{{ card.detail }}</p>
          </div>
           <p style="margin: 5px">{{ card.desc }}</p>
          <!-- INPUT -->
           <div class="input-info">
            <ComponentCheckInput v-if="card.type == 'check'" />
          </div>
            
          <div class="input-info">
            <ComponentInput v-if="card.type == 'text'" />
          </div>
          <div class="date-info">
            <ComponentDateTime v-if="card.type == 'date'" />
          </div>
          <!-- INPUT -->

         
          <!-- INPUT DATE -->
        </div>
      </div>
    </div>
</template>

<script>
import ComponentInput from "./ComponentInput.vue";
import ComponentCheckInput from "./ComponentCheckInput.vue";
import ComponentDateTime from "./ComponentDateTime.vue";

export default {
  components: {
      ComponentDateTime,
      ComponentCheckInput,
    ComponentInput,
  
 
  },
  data() {
    return {
      cards: [{
                title: "",

                type: "check",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "姓（ローマ字）",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "名（ローマ字）",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "姓（カナ）",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "名（カナ）",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "名（カナ）",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "国籍",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "在留資格",
                type: "text",
                none: false,
                isActive: true
            },
            {
                title: "",
                detail: "在留資格",
                type: "date",
                none: false,
                isActive: true
            },
            {
                title: "",
                detail: "資格外活動許可",
                type: "text",
                none: false,
                isActive: true
            },
            {
                title: "",
                detail: "就労区分",
                type: "text",
                none: false,
                isActive: true
            },
            {
                title: "",
                detail: "在留カード番号（半角）",
                type: "text",
                none: true,
                isActive: true
            },
        ],

    }
  }
    
}
  
</script>


<style scoped>
.form-3 {
    width: 515px;
    margin: 6px auto;
    background-color: #dcdcdc;
}

.date-info {
    display: flex;
}

.plus {
    display: flex;
    align-items: center;
}

.info-input-1 {
    display: flex;
    max-width: 28%;
    padding-right: 10px;
    align-items: center;
}

.check-input {
    border-radius: 50%;
    margin: 10px;
}

.info-input-1>p {
    margin-left: 10px;
}

.t1 {
    width: 20%;
}

.checkbox {
    max-width: 50%;
    margin-top: 10px;
    background-color: white;
    width: 100%;
    text-align: center;
    position: relative;
    padding: 0.875rem;
    border-right: 1px solid #dcdcdc;
}

.st-1 {
    padding: 16px;
    max-width: 480px;
    width: 100%;
    background-color: #f1f2f7;
    margin: 20px auto;
}

.st-title_p {
    display: flex;
}

.info-input {
    margin-top: 15px;
}

.st-upload {
    background: #fff;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    border-radius: 4px;
    width: 100%;
    padding: 1rem 0.71rem;
}

.title-button {
    width: 515px;
    margin: 6px auto;
}

.p-1 {
    margin-right: 10px;
    background: red;
    color: white;
    padding: 2px;
    border-radius: 3px;
    font-weight: 700;
}

.p-2 {
    background: #b2b1ff;
}

.p-3 {
    display: none;
}

button {
    width: 100%;
    border: none;
    height: 60px;
    margin-bottom: 60px;
    cursor: pointer;
    background: #b2b1ff;
    color: white;
    font-size: 20px;
    font-weight: 700;
}

.st-title {
    margin-bottom: 25px;
}

.inpt-1 {
    background: #fff;
    border: 1px solid #dcdcdc;
    box-sizing: border-box;
    border-radius: 4px;
    padding: 0.57rem 0.71rem;
    width: 95%;
    margin: 0 auto;
}

input {
    border: none;
    width: 100%;
    font-size: 1rem;
    line-height: 1.5rem;
    color: #333;
}

button {
    width: 100%;
    border: none;
    height: 60px;
    margin-bottom: 60px;
    cursor: pointer;
    background: #b2b1ff;
    color: white;
    font-size: 20px;
    font-weight: 700;
}

.mt-2 {
    display: flex;
    padding: 20px;
}

.mt-1 {
    background: #fff;
    border: 1px solid #dcdcdc;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    border-radius: 4px;
    padding: 0.57rem 0.71rem;
    width: 95%;
    margin: 5px auto;
}

.form-1 {
    height: 111px;
    width: 500px;
    margin: 6px auto;
    background-color: #f1f2f7;
}

.form-3 {
    width: 500px;
    margin: 6px auto;
    background-color: #f1f2f7;
    min-height: 690px;
}

.first-step {
    margin-top: 20px;
    padding-bottom: 14px;
}

p {
    margin: 0;
}
</style>