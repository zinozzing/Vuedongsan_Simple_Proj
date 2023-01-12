<template>
  <div>
    <img :src="roomData[num].image" class="room-img" />
    <h4 class="font-bold">{{ roomData[num].title }}</h4>
    <p>{{ roomData[num].price }}원</p>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    roomData: Array,
    num: Number,
  },
  data() {
    return {};
  },
};
</script>

<style>
.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
