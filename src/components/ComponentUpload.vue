<template>
  <div class="">
    <div class="st-upload">
      <div class="st-img">
        <img src="../assets/uploadI.png" alt="" />
      </div>
      <div class="st-p">
        <p style="font-weight: 900">ファイルをドラッグ&プするか、</p>
        <p>ドロップ ファイルをドロッ</p>
        <p>ファイルを参照する</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.st-img {
  text-align: center;
}
.st-p {
  text-align: center;
}
p {
  margin: 0;
}
.st-upload {
  background: #fff;
 
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border-radius: 4px;
  width: 100%;
  padding: 1rem 0.71rem;
}
</style>
