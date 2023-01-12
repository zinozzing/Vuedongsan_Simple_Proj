<template>
  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <!-- <button class="close font-bold" @click="modalOpen = !modalOpen">X</button> -->
      <img :src="roomData[modalNum].image" alt="" />
      <h4 class="font-bold">{{ roomData[modalNum].title }}</h4>
      <p>{{ roomData[modalNum].content }}</p>
      <p>{{ roomData[modalNum].price }}원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: {
    roomData: Array,
    modalNum: Number,
    modalOpen: Boolean,
  },
  data() {
    return {};
  },
};
</script>

<style>
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.close {
  margin-left: 90%;
}
</style>
