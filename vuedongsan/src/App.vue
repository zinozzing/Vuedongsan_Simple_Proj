<template>
  <Modal :roomData="roomData" :modalNum="modalNum" :modalOpen="modalOpen" />
  <div class="menu">
    <a href="" v-for="(tab, i) in menu" :key="i">{{ tab }}</a>
  </div>
  <Discount />
  <Card
    :roomData="roomData"
    :num="roomData[0].id"
    @click="
      modalOpen = true;
      modalNum = roomData[0].id;
    "
  />
  <Card
    :roomData="roomData"
    :num="roomData[1].id"
    @click="
      modalOpen = true;
      modalNum = roomData[1].id;
    "
  />
  <Card
    :roomData="roomData"
    :num="roomData[2].id"
    @click="
      modalOpen = true;
      modalNum = roomData[2].id;
    "
  />
  <Card
    :roomData="roomData"
    :num="roomData[3].id"
    @click="
      modalOpen = true;
      modalNum = roomData[3].id;
    "
  />
  <Card
    :roomData="roomData"
    :num="roomData[4].id"
    @click="
      modalOpen = true;
      modalNum = roomData[4].id;
    "
  />
  <Card
    :roomData="roomData"
    :num="roomData[5].id"
    @click="
      modalOpen = true;
      modalNum = roomData[5].id;
    "
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
      modalNum: 0,
      modalOpen: false,
      menu: ["Home", "Shop", "About"],
      products: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
      roomData: oneroom,
    };
  },
  methods: {
    increase(idx) {
      this.report[idx]++;
    },
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
