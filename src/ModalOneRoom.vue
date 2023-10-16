<template>
<div class="black-bg" v-if="modal==true" >
    <div class="white-bg">
      <h4>{{oneRooms[oneroom].title}}</h4>
      <img :src="oneRooms[oneroom].image">
      <p>{{oneRooms[oneroom].content}}</p>
      <p>{{oneRooms[oneroom].price}}</p>
      <input v-model.number="month">
      <p>{{month}}개월 선택 : {{oneRooms[oneroom].price*month}}</p>
      <button @click="closeModal">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name:'ModalOneRoom',
  data(){
    return {
      month:3
    }
  },
  props:{
    oneRooms: Array,
    oneroom:Number,
    modal:Boolean
  },
  methods:{
    closeModal(){
      this.$emit("closeModal");
    }
  },
  beforeUpdate(){
    if(this.month<3){
      alert('최소 3개월부터 계약 가능합니다.');
      this.month=3;
    }
  }
}
</script>

<style>

</style>