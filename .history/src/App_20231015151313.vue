<template>
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{a}}</a>
  </div>

  <DiscountOneRoom />

  <OneRoom :oneRoom="oneRoom" v-for="(oneRoom,i) in 원룸들" :key="i" @openModal="모달창열렸니=true" />



</template>

<script>
import DiscountOneRoom from './DiscountOneRoom.vue';
import OneRoom from './OneRoom.vue';

import data from './oneroom.js';
export default {
  components: { DiscountOneRoom ,OneRoom},
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
