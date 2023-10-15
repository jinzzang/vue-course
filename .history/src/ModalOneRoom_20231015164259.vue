<template>
<div class="black-bg" v-if="모달창열렸니==true">
    <div class="white-bg">
      <h4>{{원룸들[원룸].title}}</h4>
      <img :src="원룸들[원룸].image">
      <p>{{원룸들[원룸].content}}</p>
      <p>{{원룸들[원룸].price}}</p>
      <input v-model.number="month">
      <p>{{month}}개월 선택 : {{원룸들[원룸].price+month}}</p>
      <button @click="closeModal">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name:'ModalOneRoom',
  data(){
    return {
      month: 1
    }
  },
  watch:{
    month(a){
      if(a>12){
        alert("fuck me");
      }else if(typeof a !== "number"){
        alert("숫자만 입력하세요. 뒤집니다.");
      }
    }
  },
  props:{
    원룸들: Array,
    원룸:Number,
    모달창열렸니:Boolean
  },
  methods:{
    closeModal(){
      this.$emit("closeModal");
    }
  }
}
</script>

<style>

</style>