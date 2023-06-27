<template>
<div v-if="!isClose" class="baner">
  <div class="text">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Alias consequatur deleniti impedit optio repudiandae similique.
  </div>
  <div  @click="isClose = true" class="close">
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M18 7.05L16.95 6L12 10.95L7.05 6L6 7.05L10.95 12L6 16.95L7.05 18L12 13.05L16.95 18L18 16.95L13.05 12L18 7.05Z" fill="white"/>
    </svg>
  </div>
</div>
</template>

<script>
export default {
  name: "bottomElem",
  data() {
    return {
      isClose: false
    }
  }
}
</script>

<style scoped>
.baner {
  max-width: 960px;
  width: 960px;
  margin: auto;
  position: relative;
  right: 0;
  left: 0;
  height: 60px;
  margin-top: -60px;
  border-radius: 12px;
  border: 1px solid var(--primary-border, #4D4D4D);
  background: var(--seondary-bg, #262626);
  padding: 10px;
  box-sizing: border-box;
}
.text {
  width:fit-content;
  border-radius: 12px;
  color: rgba(0,0,0,0);
  background: var(--skeleton, linear-gradient(90deg, #3C3C3C 0%, #444 51.04%, #333 100%));
  height: 100%;
}
.close {
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