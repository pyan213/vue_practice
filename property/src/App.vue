<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a, i) in 메뉴들" :key="i">{{ a }}</a>
  </div>

  <div v-for="(product, i) in 원룸들" :key="i">
    <img :src="product.image" class="room-img">
    <h4>{{ product.title }}</h4>
    <p>{{ product.price }} 원</p>
  </div>

  <!-- <div>
    <img :src="원룸들[0].image" class="room-img">
    <h4>{{ 원룸들[0].title }}</h4>
    <p>{{ 원룸들[0].price }}원</p>
  </div>

  <div>
    <img src="./assets/room1.jpeg" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>60 만원</p>
    <button v-on:click="신고수[1]++">허위매물신고</button> <span>신고수: {{ 신고수[1] }}</span>
  </div>

  <div>
    <img src="./assets/room2.jpeg" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>70 만원</p>
    <button v-on:click="신고수[2]++">허위매물신고</button> <span>신고수: {{ 신고수[2] }}</span>
  </div> -->

</template>

<script>

import data from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      원룸들: data,
      모달창열렸니: false,
      신고수: [0, 0, 0],
      메뉴들: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods: {
    increase() {
      this.신고수 += 1;
    },
  },
  components: {
  }
}
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

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
}
</style>
