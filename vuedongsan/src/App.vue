<template>
  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <button class="close" @click="modalOpen = !modalOpen">닫기</button>
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
    <h4>{{ products[0] }} 원룸</h4>
    <p>50 만원</p>
    <button @click="increase(0)">허위매물신고</button>
    <span>신고수 : {{ report[0] }}</span>
  </div>
  <div>
    <img
      src="./assets/room1.jpg"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4>{{ products[1] }} 원룸</h4>
    <p>70 만원</p>
    <button @click="increase(1)">허위매물신고</button>
    <span>신고수 : {{ report[1] }}</span>
  </div>
  <div>
    <img
      src="./assets/room2.jpg"
      alt=""
      class="room-img"
      @click="modalOpen = !modalOpen"
    />
    <h4>{{ products[2] }} 원룸</h4>
    <p>80 만원</p>
    <button @click="increase(2)">허위매물신고</button>
    <span>신고수 : {{ report[2] }}</span>
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
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
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
