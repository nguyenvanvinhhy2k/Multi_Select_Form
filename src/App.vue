<template>
  <div id="app">
    <div class="header">
      <div class="logo">
        <img src="./assets/logoo.png" alt="" />
      </div>
      <div class="menu">
        <ul>
          <li style="font-weight: 900">入社手続き</li>
          <li>ヘルプ</li>
        </ul>
      </div>
    </div>
    <div class="form-wrap">
      <div class="section">
        <div class="content-wrap">
          <div class="content-title">
            <div class="link">
              <img
                v-if="steps > 1"
                @click="pervStep"
                class="img"
                src="./assets/ArrowLeft.svg"
                alt=""
              />

              <h3>雇用契約に戻る</h3>
            </div>
            <h2 style="margin: 0 12px; font-size: 28px">雇用契約について</h2>
          </div>
          <div class="icon-steps">
            <StepsIcon :steps="steps" :totalSteps="totalSteps"></StepsIcon>
          </div>
          <div class="date">
            <img
              class="icon-date"
              style="margin-bottom: 15px"
              src="./assets/date.png"
              alt=""
            />
          </div>
        </div>
      </div>
      <div class="notice">
        <div class="notice-header">
          <div class="icon">
            <img
              style="width: 25px; margin-right: 10px"
              src="./assets/frame.svg"
              alt=""
            />
          </div>
          <div class="notice-title">
            <h3>ご確認ください</h3>
          </div>
        </div>

        <div class="notice-content">
          <h3 style="font-weight: 400; margin: 0">
            表示されている内容を確認いただき、認識に相違が無ければ同意するにチェックをしてください。
          </h3>
        </div>
      </div>
      <div class="step-1" v-if="steps === 1">
        <FirstStep @nextStep="nextStep"></FirstStep>
      </div>
      <div class="step-2" v-if="steps === 2">
        <SecondStep @nextStep="nextStep"></SecondStep>
      </div>

      <div class="step-3" v-if="steps === 3">
        <ThirdStep></ThirdStep>
      </div>
    </div>
  </div>
</template>

<script>
import FirstStep from "./components/firstStep.vue";
import StepsIcon from "./components/StepsIcon.vue";
import SecondStep from "./components/SecondStep.vue";
import ThirdStep from "./components/ThirdStep.vue";
export default {
  name: "App",
  components: { StepsIcon, FirstStep, SecondStep, ThirdStep },
  data() {
    return {
      steps: 1,
      totalSteps: 5,
    };
  },
  methods: {
    nextStep() {
      this.steps++;
    },
    pervStep() {
      this.steps--;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0;
  padding: 0;
}
.notice {
  width: 500px;
  margin: 0 auto;
  background-color: #f1f2f7;
}
.form-wrap {
  width: 600px;
  margin: 0 auto;
}
.notice-header {
  display: flex;
  align-items: center;
}

.form-2 {
  width: 500px;
  margin: 6px auto;
  background-color: #f1f2f7;
}
.icon-steps {
  padding: 20px 0;
}
.section {
  width: 100%;
}
.content-wrap {
  position: relative;
  max-width: 500px;
  margin: 0 auto;
  padding-top: 20px;
}
.icon-date {
  width: 60%;
}
.header {
  width: 1440px;
  height: 64px;
  left: calc(50% - 1440px / 2);
  display: flex;
  align-items: center;
}
ul {
  display: flex;
}
li {
  margin-right: 20px;
  font-size: 20px;
  list-style: none;
}
.img-icon {
  width: 40px;
  height: 40px;
  left: calc(50% - 40px / 2 - 265px);
  top: 168px;
  margin-right: 41px;
  border-radius: 50%;
  background: #b2b1ff;
}
.icon-steps::after {
  content: "";
  width: 23.43rem;
  height: 2px;
  display: block;
  background-color: #f1f2f7;
  position: absolute;
  top: 65.5%;
  left: 8%;
  transform: translateY(-50%);
}
.img {
  width: 30px;
  padding-right: 10px;
}
.notice-content {
  padding: 10px;
}
.logo {
  width: 80px;
}
img {
  width: 63px;
  cursor: pointer;
  margin-left: 15px;
}
.link {
  display: flex;
}
</style>
