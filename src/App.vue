<script setup>
import CenterE from "@/components/center.vue";
import Left from "@/components/left.vue";
import BottomElem from "@/components/bottomElem.vue";
</script>

<template>
  <div class="elem">
<left />
  <center-e />
  </div>
  <bottom-elem/>
</template>

<style scoped>
.elem {
  display: flex;
  margin: auto;
  height: 700px;
  width: 1270px;
  padding: 20px;
  max-height: 600px;
  max-width: 1270px;
  justify-content: center;
}
</style>
