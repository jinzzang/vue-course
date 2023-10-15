<template>

  <div class="" v-if="1 == 2">조진호</div>
  <div class="" v-else-if="1 < 3">큼</div>
  <div class="" v-else>입니다.</div>
  
  <ModalOneRoom :원룸들="원룸들" :원룸="원룸" :모달창열렸니="모달창열렸니"/>


  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{a}}</a>
  </div>

  <DiscountOneRoom/>

  <div v-for="(oneRoom,i) in 원룸들" :key="i" @click="모달창열렸니=true;원룸=i">
    <img :src="oneRoom.image" class="room-img"/>
    <h4>{{oneRoom.title}} </h4>
    <p>{{oneRoom.price}} 원</p>
  </div>



</template>

<script>
import DiscountOneRoom from './DiscountOneRoom.vue';
import ModalOneRoom from './ModalOneRoom.vue';

import data from './oneroom.js';
export default {
  components: { DiscountOneRoom, ModalOneRoom },
  name: 'App',
  data(){
    return {
      모달창열렸니 : false,
      원룸들:data,
      원룸:0
    }
  }

};
</script>

<style>
body{
  margin :0
}

div{
  box-sizing: border-box;
}

.black-bg{
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg{
  width:100%;
  background: white;
  border-radius: 8px;
  padding:20px;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu{
  display:flex;
  justify-content: space-around;
  background-color: darkslateblue;
  padding: 2rem;
  color: white;
  border-radius: 1.5rem;
}

.room-img{
 width:100%;
 margin-top:40px;
}
</style>
