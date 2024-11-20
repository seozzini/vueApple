<template>
  <!-- <div v-if="1 == 2">안녕하세요</div>
  <div v-else-if="1 == 3">안녕하세요2</div>
  <div v-else>안녕하세요3</div> -->

  <ModalModal />

  <div class="menu">
    <a v-for="(a, i) in menus" :key="i">{{ a }}</a>
  </div>

  <DisCount />

  <!-- <div v-for="(b,j) in products" :key="j">
    <h4>{{ b }}</h4>
    <p>50 만원</p>
</div> -->
  <div v-for="(a, i) in onerooms" :key="i">
    <img :src="a.image" class="room-img" />
    <h4
      @click="
        modalState = true;
        누른거 = i;
      "
    >
      {{ a.title }}
    </h4>
    <p>{{ a.price }}원</p>
    <button @click="singo[i]++">허위매물신고</button
    ><span> 신고 수 : {{ singo[i] }}</span>
  </div>

  <!-- <div>
    <img :src="onerooms[0].image" class="room-img">
    <h4 @click="modalState = true">{{ onerooms[0].title }}</h4>
    <p>{{onerooms[0].price}}원</p>
    <button @click ="singo[0]++">허위매물신고</button><span> 신고 수 : {{ singo[0] }}</span>
  </div>
  <div>
    <img :src="onerooms[1].image" class="room-img">
    <h4 @click="modalState = true">{{ onerooms[1].title }}</h4>
    <p>{{onerooms[1].price}}원</p>
    <button @click ="singo[1]++">허위매물신고</button><span> 신고 수 : {{ singo[1] }}</span>
  </div>
  <div>
    <img :src="onerooms[2].image" class="room-img">
    <h4 @click="modalState = true">{{ onerooms[2].title }}</h4>
    <p>{{onerooms[2].price}}원</p>
    <button @click ="singo[2]++">허위매물신고</button><span> 신고 수 : {{ singo[2] }}</span>
  </div>
  <div>
    <img :src="onerooms[3].image" class="room-img">
    <h4 @click="modalState = true">{{ onerooms[3].title }}</h4>
    <p>{{onerooms[3].price}}원</p>
    <button @click ="singo[3]++">허위매물신고</button><span> 신고 수 : {{ singo[3] }}</span>
  </div>
  <div>
    <img :src="onerooms[4].image" class="room-img">
    <h4 @click="modalState = true">{{ onerooms[4].title }}</h4>
    <p>{{onerooms[4].price}}원</p>
    <button @click ="singo[4]++">허위매물신고</button><span> 신고 수 : {{ singo[4] }}</span>
  </div>
  <div>
    <img :src="onerooms[5].image" class="room-img">
    <h4 @click="modalState = true">{{ onerooms[5].title }}</h4>
    <p>{{onerooms[5].price}}원</p>
    <button @click ="singo[5]++">허위매물신고</button><span> 신고 수 : {{ singo[5] }}</span>
  </div> -->
</template>

<script>
import oneroomData from './assets/oneroom.js';
import DisCount from './components/DisCount.vue';
import ModalModal from './components/ModalModal.vue';
oneroomData;

export default {
  name: 'App',
  data() {
    return {
      누른거: 0,
      onerooms: oneroomData,
      modalState: false,
      singo: [0, 0, 0, 0, 0, 0],
      menus: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      prices: [50, 60, 70],
    };
  },
  methods: {
    increase() {
      this.singo++;
    },
  },
  components: {
    DisCount,
    ModalModal,
  },
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
.black-bg {
  width: 100%;
  height: 100px;
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

.room-img {
  width: 80%;
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
