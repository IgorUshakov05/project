<template>
  <div class="modal">
    <div @click="sendMessage" class="close">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M18 7.05L16.95 6L12 10.95L7.05 6L6 7.05L10.95 12L6 16.95L7.05 18L12 13.05L16.95 18L18 16.95L13.05 12L18 7.05Z" fill="white"/>
      </svg>
    </div>
    <div class="pic">
    <img :src="imageUrl" alt="">
    </div>
      <hr>
    <div class="content">
      <div class="title">

      </div>
      <div class="desription first">21313331123123123123</div>
      <div class="desription">awdada2323232323wd</div>
      <div class="desription">12312312312233123</div>
      <div class="desription">123123123123wdawdawdawd</div>
      <div class="desription">123123123123dawdawd</div>
      <hr>
    </div>
    <button  class="button">Удалить предмет</button>
  </div>
</template>

<script>
export default {
  name: "right",
  props: {
    imageUrl: {
      type: String,
      required: true
    },
    Number: {
      type: Number,
      required: true
    }
  },
  methods: {
    sendMessage() {
      this.$emit('messageSent', false);
    }
  }
}
</script>

<style scoped>
button  {
  border-radius: 8px;
  background: var(--red-hover, #F88);
}
hr {
  width: 86%;
  background: var(--primary-border, #4D4D4D);
  border: none;
  height: 1.5px;
}
.pic {
  width: 100%;
  height: auto;
  margin: auto;
  padding: 60px 60px 20px 60px;
  box-sizing: border-box;
}

.button {
  color:  #FFF;
  text-align: center;
  /* Tg-Btn */
  font-size: 14px;
  width: 90%;
  position: absolute;
  right: 0;
  left: 0;
  margin: auto;
  bottom: 0;
  border: none;
  height: 50px;
  margin-bottom: 20px;
}

.pic > img {
  width: 100%;
  height: auto;
}
.modal {
  width: 270px;
  height: 537px;
position: absolute;
  margin-right: -680px;
  border-radius: 0 12px 12px 0;
  border: 1px solid #4D4D4D;
  border-left: 1px solid var(--primary-border, #4D4D4D);
  background: rgba(38, 38, 38, 0.50);
  backdrop-filter: blur(8px);
}
.content {
  height: fit-content;
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

.close {
  padding: 5px;
  width: 30px;
  height: 30px;
  position: absolute;
  z-index: 20;
  right: 2px;
  top: 0px;
}
.close > svg {
  width: 100%;
  height: 100%;
}
</style>
