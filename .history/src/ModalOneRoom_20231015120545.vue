<template>
<div class="black-bg" v-if="모달창열렸니==true">
    <div class="white-bg">
      <h4>{{원룸들[원룸].title}}</h4>
      <img :src="원룸들[원룸].image">
      <p>{{원룸들[원룸].content}}</p>
      <p>{{원룸들[원룸].price}}</p>
      <!-- <button @click="모달창열렸니=false">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
  name:'ModalOneRoom',
  data(){
    return {

    }
  },
  props:{
    원룸들: Array,
    원룸:Number,
    모달창열렸니:Boolean
  }
}
</script>

<style>

</style>