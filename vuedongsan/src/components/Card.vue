<template>
  <div>
    <img :src="roomData.image" class="room-img" />
    <h4 class="font-bold" @click="$emit('openModal')">{{ roomData.title }}</h4>
    <p>{{ roomData.price }}원</p>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    roomData: Object,
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
