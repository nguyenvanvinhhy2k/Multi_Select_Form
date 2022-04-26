<template>
  <div class="">
    <h1>ThirdStep</h1>
    <div class="form-2" style="height: 60px">
      <button @click="submit">入社手続きの入力に進む</button>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    submit() {
      this.$emit("nextStep");
    },
  },
};
</script>

<style scoped>
.form-2 {
  width: 500px;
  margin: 6px auto;
  background-color: #dcdcdc;
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
</style>
