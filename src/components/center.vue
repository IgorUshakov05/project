<template>
  <div class="reshetka">

    <div class="square" @dragover.prevent @drop="drop">
      <div v-if="one" @click="activModal('@/assets/green.png')" class="square" @dragstart="dragStart" draggable="true">
        <img src="@/assets/green.png" alt="" draggable="false">
        <div class="num"><span>2</span></div>
      </div>
    </div>
    <div class="square" @dragover.prevent @drop="drop">
      <div v-if="two" @click="activModal('@/assets/yellow.png')" class="square" @dragstart="dragStart" draggable="true">
        <img src="@/assets/yellow.png" alt="" draggable="false">
        <div class="num"><span>4</span></div>
      </div>
    </div>
    <div class="square" @dragover.prevent @drop="drop">
      <div v-if="three" @click="activModal('@/assets/purple.png')" class="square" @dragstart="dragStart" draggable="true">
        <img src="@/assets/purple.png" draggable="false" alt="">
        <div class="num"><span>10</span></div>
      </div>
    </div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
    <div class="square" @dragover.prevent @drop="drop"></div>
  </div>
  <right v-if="modal" @messageSent="handleMessage" :image-url="pic" />
</template>
  <script>
import Right from "@/components/right.vue";

export default {
  name: "centerE",
  components: {Right},
  data() {
    return {
    modal: false,
      pic: '@/assets/purple.png',
      one: true,
      two: true,
      three: true
    }
  },
  methods: {
    activModal(imageUrl) {
      this.modal =true;
      this.pic = imageUrl;
    },
    handleMessage(status) {
      this.modal = status;
    }
    },
  mounted() {
    setInterval(() => {
      // Получение элемента "reshetka" и его HTML-кода
      const reshetkaElement = document.querySelector(".reshetka");
      const htmlCode = reshetkaElement.outerHTML;


// Сохранение HTML-кода в localStorage
      localStorage.setItem("savedHTML", htmlCode);

    },1000)
    const squares = document.querySelectorAll(".square");

    let draggedItem = null;

    function dragStart(event) {
      draggedItem = event.target;
    }

    function dragOver(event) {
      event.preventDefault();
    }

    function drop(event) {
      const target = event.target;
      const source = draggedItem;

      if (!target.classList.contains("square")) return;

      if (target.querySelector("img")) return;

      target.appendChild(source);
      draggedItem = null;
    }

    squares.forEach((square) => {
      square.addEventListener("dragstart", dragStart);
      square.addEventListener("dragover", dragOver);
      square.addEventListener("drop", drop);
    });
  },
};
</script>

<style scoped>
.num {
  position: absolute;
  margin-bottom: -84px;
  text-align: center;
  width: 20px;
  color: var(--primary-white, #FFF);
  text-align: center;
  box-sizing: border-box;
  padding: 3px;
  font-size: 12px;

  font-weight: 500;
  border: 1px solid #4D4D4D;
  margin-right: -104px;
  border-radius: 10px 0 0 0;
  height: 20px;
}
.reshetka {
  margin-left: 40px;
  width: 50%;
  background: #262626;
  height: 90%;
  border: 1px solid #4D4D4D;
  border-radius: 12px;
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  gap: 5px;
  box-sizing: border-box;
  overflow: hidden;
}

.square {
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  cursor: grab;
  width: 100%;
  height: 100%;
  border: 1px solid #4D4D4D;
}

.square > img {
  width: 70px;
  height: 70px;
}

.square:active{
  border-radius: 20px;
  border: 1px solid var(--primary-border, #4D4D4D);
  background: var(--seondary-bg, #262626);
  cursor: grabbing !important;
}
.square:active > .num {
  opacity: 0;
}

</style>