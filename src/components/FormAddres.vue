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
        <div class="info-input" v-for="addres in address" :key="addres">
          <div class="st-title_p">
            <p :class="{'p-2':!addres.isActive,'p-3':!addres.none}"  class="p-1">必須</p>
            <p>{{ addres.detail }}</p>
          </div>
           <p style="margin: 5px">{{ addres.desc }}</p>
          <!-- INPUT -->
           <div class="input-info">
            <ComponentDrop v-if="addres.type == 'drop'" />
          </div>
            <div class="date-info">
            <ComponentDateCode v-if="addres.type == 'date'" />
          </div>
          <div class="input-info">
            <ComponentInput v-if="addres.type == 'text'" />
          </div>
          <!-- INPUT -->

         
          <!-- INPUT DATE -->
        </div>
      </div>
    </div>
</template>

<script>
import ComponentInput from "./ComponentInput.vue";
import ComponentDrop from "./ComponentDrop.vue";
import ComponentDateCode from "./ComponentDateCode.vue";

export default {
  components: {
      ComponentDateCode,
      ComponentDrop,
    ComponentInput,
  
 
  },
  data() {
    return {
      address: [{
                title: "",
                detail: "姓（ローマ字）",
                type: "drop",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "姓（ローマ字）",
                type: "drop",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "郵便番号",

                type: "date",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "都道府県",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "市区町村",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "番地",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "建物名称・部屋番号",
                type: "text",
                none: false,
                isActive: true
            },
            {
                title: "",
                detail: "電話番号（半角）",
                desc: "自宅電話番号が無い場合、携帯電話番号のみ登録してください。",
                type: "text",
                none: true,
                isActive: true
            },
            {
                title: "",
                detail: "携帯電話番号（半角）",
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