<template>
  
  <div class="black-bg" v-if="모달창열렸니==true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니=false">닫기</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{a}}</a>
  </div>
  <div v-for="oneRoom in 원룸들" :key=i">
    <img :src="oneRoom[0].image" class="room-img"/>
    <h4 @click="모달창열렸니=true">{{oneRoom[0].title}} </h4>
    <p>{{oneRoom[0].price}} 원</p>
  </div>



</template>

<script>

import data from './oneroom.js';
export default {
  name: 'App',
  data(){
    return {
      모달창열렸니 : false,
      원룸들:data
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
