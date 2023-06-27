<template>
<div class="leftELem">
  <div class="img">
    <img src="@/assets/blur.png" alt="Изображение не найдено" srcset="">
  </div>
  <div class="content">
    <div class="title">

    </div>
    <div class="desription first">2131231231123123123123</div>
    <div class="desription">awdadawd</div>
    <div class="desription">123123123123123</div>
    <div class="desription">123123123123wdawdawdawd</div>
    <div class="desription">1231231231</div>
    <div class="desription">awdawd123123123</div>
  </div>
</div>
</template>

<script>
export default {
  name: "left"
}
</script>

<style scoped>
.img {
  width: auto;
  height: 50%;
  margin: auto;
}
.img > img {
  width: 100%;
  height: auto;
}
.leftELem {
  padding: 13px;
  box-sizing: border-box;
  border-radius: 12px;
  border: 1px solid #4D4D4D;
  background:#262626;
  width: 22%;
  height: 90%;
}
.content {
  height: 43%;
  margin-top: 30px;
  width: 100%;
  padding-top: 10px;
}
.title {
  width: 90%;
  margin: auto;
  height: 30px;
  border-radius: 8px;
  /*background: red;*/
  background: var(--skeleton, linear-gradient(90deg, #3C3C3C 0%, #444 51.04%, #333 100%));
}
.desription {
  height: 11px;
  border-radius: 8px;
  color: #FFFF0000;
  width: fit-content;
  margin: auto;
  margin-top: 15px;
  background: var(--skeleton, linear-gradient(90deg, #3C3C3C 0%, #444 51.04%, #333 100%));
}
.desription:last-child {
  margin-top: 30px;
}
.first {
  margin-top: 25px !important;
}
</style>