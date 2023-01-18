<template>
  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <button @click="$emit('closeModal')" class="close font-bold">X</button>
      <img :src="roomData[modalNum].image" alt="" />
      <h4 class="font-bold">{{ roomData[modalNum].title }}</h4>
      <p>{{ roomData[modalNum].content }}</p>
      <!-- <input @input="month = $event.target.value" /> -->
      <input v-model.number="month" />
      <p>{{ month }}개월 선택함 : {{ roomData[modalNum].price * month }}원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      month: 1,
    };
  },
  props: {
    roomData: Array,
    modalNum: Number,
    modalOpen: Boolean,
  },
  watch: {
    month(data) {
      if (isNaN(data)) {
        alert("숫자만 입력해주세요");
        this.month = 0;
      }
    },
  },
  beforeUpdate() {
    if (this.month == 2) {
      alert("2개월은 불가능합니다!");
      this.month = 0;
    }
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

img {
  width: 100%;
}
</style>
