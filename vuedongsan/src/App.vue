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
  <div>
    <img
      src="./assets/room0.jpg"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4 class="font-bold">{{ products[0] }}</h4>
    <p>50 만원</p>
    <button
      @click="increase(0)"
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-3 rounded"
    >
      허위매물신고
    </button>
    <span class="mx-1">신고수 : {{ report[0] }}</span>
  </div>
  <div>
    <img
      src="./assets/room1.jpg"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4 class="font-bold">{{ products[1] }}</h4>
    <p>70 만원</p>
    <button
      @click="increase(1)"
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-3 rounded"
    >
      허위매물신고
    </button>
    <span class="mx-1">신고수 : {{ report[1] }}</span>
  </div>
  <div>
    <img
      src="./assets/room2.jpg"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4 class="font-bold">{{ products[2] }}</h4>
    <p>80 만원</p>
    <button
      @click="increase(2)"
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-3 rounded"
    >
      허위매물신고
    </button>
    <span class="mx-1">신고수 : {{ report[2] }}</span>
  </div>
  <!-- <div class="products" v-for="(product, j) in products" :key="j">
    <h4>{{ product }} 원룸</h4>
    <p>가격은 아무거나</p>
  </div> -->
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      modalOpen: false,
      menu: ["Home", "Shop", "About"],
      products: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
      report: [0, 0, 0],
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
