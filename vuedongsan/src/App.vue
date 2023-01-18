<template>
  <Transition name="fade">
    <Modal
      :roomData="roomData"
      :modalNum="modalNum"
      :modalOpen="modalOpen"
      @closeModal="modalOpen = false"
    />
  </Transition>
  <div class="menu">
    <a href="" v-for="(tab, i) in menu" :key="i">{{ tab }}</a>
  </div>
  <Discount v-if="showDiscount == true" :percent="percent" />
  <div>
    <button @click="priceSort">저렴한가격순정렬</button>
  </div>
  <div>
    <button @click="priceReverseSort">비싼가격순정렬</button>
  </div>
  <div>
    <button @click="sortBack">정렬취소</button>
  </div>
  <Card
    @openModal="
      modalOpen = !modalOpen;
      modalNum = j;
    "
    v-for="(room, j) in roomData"
    :key="j"
    :roomData="room"
  />
</template>

<script>
import oneroom from "./data/room.js";
import Discount from "./DiscountBanner.vue";
import Modal from "./Modal.vue";
import Card from "./components/Card.vue";

export default {
  name: "App",
  data() {
    return {
      showDiscount: true,
      modalNum: 0,
      modalOpen: false,
      menu: ["Home", "Shop", "About"],
      products: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
      roomOriginData: [...oneroom],
      roomData: oneroom,
      percent: 30,
    };
  },
  methods: {
    priceSort() {
      this.roomData.sort((a, b) => {
        return a.price - b.price;
      });
    },
    priceReverseSort() {
      this.roomData.sort((a, b) => {
        return b.price - a.price;
      });
    },
    sortBack() {
      this.roomData = [...this.roomOriginData];
    },
  },

  mounted() {
    setInterval(() => {
      this.percent = this.percent - 1;
      if (this.percent == 0) {
        this.showDiscount = false;
      }
    }, 1000);
  },

  components: {
    Discount,
    Modal,
    Card,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.fade-leave-from {
  opacity: 1;
}

.fade-leave-active {
  transition: all 1s;
}

.fade-leave-to {
  opacity: 0;
}

/* 시작 */
.fade-enter-from {
  opacity: 0;
}

.fade-enter-active {
  transition: all 1s;
}

/* 에니메이션의 종료 */
.fade-enter-to {
  opacity: 1;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
  text-decoration: none;
}

body {
  margin: 0;
}
</style>
