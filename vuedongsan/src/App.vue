<template>
  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <button class="close font-bold" @click="modalOpen = !modalOpen">X</button>
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>

  <div class="menu">
    <a href="" v-for="(tab, i) in menu" :key="i">{{ tab }}</a>
  </div>
  <!-- <div>
    <img
      :src="roomData[0].image"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4 class="font-bold">{{ roomData[0].title }}</h4>
    <p>{{ roomData[0].price }}원</p>
  </div>
  <div>
    <img
      :src="roomData[1].image"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4 class="font-bold">{{ roomData[1].title }}</h4>
    <p>{{ roomData[1].price }}원</p>
  </div>
  <div>
    <img
      :src="roomData[2].image"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4 class="font-bold">{{ roomData[2].title }}</h4>
    <p>{{ roomData[2].price }}원</p>
  </div> -->
  <div v-for="(prod, i) in roomData" :key="i">
    <img :src="prod.image" class="room-img" @click="modalOpen = !modalOpen" />
    <h4 class="font-bold">{{ prod.title }}</h4>
    <p>{{ prod.price }}원</p>
  </div>
</template>

<script>
import oneroom from "./data/room.js";
export default {
  name: "App",
  data() {
    return {
      modalOpen: false,
      menu: ["Home", "Shop", "About"],
      products: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
      report: [0, 0, 0],
      roomData: oneroom,
    };
  },
  methods: {
    increase(idx) {
      this.report[idx]++;
    },
  },
  components: {},
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}
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
