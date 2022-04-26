<template>
  <div class="">
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 10px">ご確認ください</h3>
        <p>
          システムの本人アイコンに使用します。あなたの顔が分かる写真を登録してください。未登録の場合、姓名の頭文字が表示されます。顔写真見本のように撮影してください。また、背景は白、スーツ着用、身だしなみルールに沿って撮影をお願いいたします。
        </p>
      </div>
      <div class="st-upload">
        <ComponentUpload />
      </div>
    </div>
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 10px">ご確認ください</h3>
        <div class="st-title_p">
          <p class="p-1">必須</p>
          <p>運転免許証両面もしくは住民票を添付してください。</p>
        </div>
      </div>
      <div class="st-upload">
        <ComponentUpload />
      </div>
    </div>
    <!-- Form 1 -->
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
            <p class="p-1">必須</p>
            <p>{{ info.detail }}</p>
          </div>
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
    <!-- Form 1 -->
    <!-- Form 2 -->
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 0">最終学歴</h3>
        <div class="st-title_p">
          <p>
            最終学歴が大学院の方は、大学を登録後に「＋学歴を追加する」から大学院を登録してください。
          </p>
        </div>
        <p style="margin: 0; font-weight: 900">学歴1</p>
      </div>

      <div class="">
        <div
          class="info-input"
          v-for="education in educations"
          :key="education"
        >
          <div class="st-title_p">
            <p class="p-1">必須</p>
            <p>{{ education.detail }}</p>
          </div>

          <div class="input-info">
            <ComponentDateTime v-if="education.type == 'date'" />
          </div>
          <div class="input-info">
            <ComponentDrop
              v-if="education.type == 'drop'"
              style="position: relative"
            />
          </div>
          <div class="input-info">
            <ComponentInput v-if="education.type == 'text'" />
          </div>
        </div>
        <div class="plus">
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
    <!-- Form 2 -->
    <!-- Form 3 -->
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 0; font-weight: 100">保険年金</h3>
      </div>

      <div class="">
        <div class="info-input" v-for="pension in pensions" :key="pension">
          <div class="st-title_p" style="display: block">
            <div class="" style="display: flex">
              <p class="p-1" v-if="pension.isReq">必須</p>

              <p style="font-weight: 700">{{ pension.detail }}</p>
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
    <!-- Form 3 -->

    <!-- Form 4 -->
    <div class="st-1">
      <div class="st-title">
        <h3 style="margin: 0; font-weight: 100">給与振込口座</h3>
      </div>

      <div class="">
        <div class="info-input" v-for="payroll in payrolls" :key="payroll">
          <div class="st-title_p" style="display: block">
            <div class="" style="display: flex; margin: 0">
              <p class="p-1">必須</p>

              <p style="font-weight: 700">{{ payroll.detail }}</p>
            </div>
            <p style="margin-top: 0">{{ payroll.desc }}</p>
          </div>

          <div class="check-info">
            <ComponentSearch v-if="payroll.type == 'search'" />
          </div>
          <div class="check-info">
            <ComponentInput v-if="payroll.type == 'text'" />
          </div>
        </div>
      </div>
    </div>
    <!-- Form 4 -->
    <div class="form-3" style="height: 60px">
      <button @click="submit">入社手続きの入力に進む</button>
    </div>
  </div>
</template>

<script>
import ComponentDrop from "./ComponentDrop.vue";
import ComponentDateTime from "./ComponentDateTime.vue";
import ComponentDate from "./ComponentDate.vue";
import ComponentCheck from "./ComponentCheck.vue";
import ComponentUpload from "./ComponentUpload.vue";
import ComponentInput from "./ComponentInput.vue";
import ComponentSearch from "./ComponentSearch.vue";
export default {
  components: {
    ComponentUpload,
    ComponentSearch,
    ComponentInput,
    ComponentCheck,
    ComponentDate,
    ComponentDateTime,
    ComponentDrop,
  },
  data() {
    return {
      infos: [
        { title: "", detail: "姓", type: "text" },
        { title: "", detail: "名", type: "text" },
        { title: "", detail: "姓", type: "text" },
        { title: "", detail: "セイ", type: "text" },
        { title: "", detail: "メイ", type: "text" },
        { title: "", detail: "姓（ローマ字）", type: "text" },
        { title: "", detail: "性別", type: "check" },
        { title: "", detail: "生年月日", type: "date" },
        { title: "", detail: "ビジネスネーム", type: "text" },
      ],
      educations: [
        { title: "", detail: "入学年月日", type: "date" },
        { title: "", detail: "卒業年月日", type: "date" },
        { title: "", detail: "卒業年月日", type: "drop" },
        { title: "", detail: "卒業年月日", type: "text" },
        { title: "", detail: "卒業年月日", type: "text" },
      ],
      pensions: [
        { title: "", detail: "基礎年金番号", isReq: true, type: "text" },
        {
          title: "",
          detail: "雇用保険被保険者番号",
          desc: "番号をお持ちの方は必ず入力してください",
          type: "text",
        },
        {
          title: "",
          detail: "前職会社名",
          desc: "雇用保険番号が不明の場合は入力をしてください",
          type: "text",
        },
        {
          title: "",
          detail: "資格証明書類（年金手帳",
          desc: "年金手帳の写真を添付してください",
          type: "upload",
        },
        {
          title: "",
          detail: "資格署名書類（雇用保険被保険者証",
          desc: "雇用保険被保険者証の写真を添付してください",
          type: "upload",
        },
        { title: "", detail: "確定拠出年金の利用希望", type: "check" },
      ],
      payrolls: [
        {
          title: "",
          detail: "金融機関をフリーワードで検索",
          desc: "｢とうきょう｣や｢しんよう｣などの一単語のみで検索できます",
          type: "search",
        },
        {
          title: "",
          detail: "支店名をフリーワードで検索",
          desc: "｢しんじゅく｣や｢しぶや｣などの一単語のみで検索できます",
          type: "search",
        },
        {
          title: "",
          detail: "口座番号（半角）",

          type: "text",
        },
        {
          title: "",
          detail: "口座名義（カタカナ）",
          desc: "本人名義に限ります",
          type: "text",
        },
      ],
    };
  },
  methods: {
    submit() {
      this.$emit("nextStep");
    },
  },
};
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
.info-input-1 > p {
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
.p-1 {
  margin-right: 10px;
  background: red;
  color: white;
  padding: 2px;
  border-radius: 3px;
  font-weight: 700;
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
</style>
