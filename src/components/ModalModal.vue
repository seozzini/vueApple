<template>
  <div class="black-bg" v-if="modalState == true">
    <div class="white-bg">
      <img :src="onerooms[누른거].image" />
      <h4>{{ onerooms[누른거].title }}</h4>
      <p>{{ onerooms[누른거].content }}</p>
      <p>가격: {{ onerooms[누른거].price }}원</p>
      <DisCount />
      <!-- <button @click="modalState = false">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalModal',
  props: {
    onerooms: Array,
    누른거:Number,
    modalState: Boolean,
  }
};
</script>
