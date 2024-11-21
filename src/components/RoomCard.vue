<!-- components/RoomCard.vue -->

<template>

<div>
  <img :src="oneRoom.image" class="room-img" />
  <h4>
    {{ oneRoom.title }}
  </h4>
  <p>{{ oneRoom.price }}원</p>
</div>

</template>

<script>

export default{
  name:'RoomCard',
  props: {
    oneRoom: Object,

  }
  
}

</script>

