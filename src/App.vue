<template>
  <Transition name="fade">
    <ModalOneRoom :oneRooms="oneRooms" :oneroom="oneroom" :modal="modal" @closeModal="modal=false"/>
  </Transition>


  <div class="menu">
    <a v-for="a in menu" :key="a">{{a}}</a>
  </div>

  <DiscountOneRoom :discountValue="discountValue" v-if=" showDiscount == true "/>

  <button @click="printSort()">가격순버튼</button>
  <button @click="sortBack()">되돌리기</button>
  <OneRoom1 :oneRoom="oneRoom" v-for="(oneRoom,i) in oneRooms" :key="i" @openModal="modal=true; oneroom=$event"/>




</template>

<script>
import DiscountOneRoom from './DiscountOneRoom.vue';
import ModalOneRoom from './ModalOneRoom.vue';
import OneRoom1 from './OneRoom1.vue';

import data from './oneroom.js';
export default {
  components: { DiscountOneRoom, ModalOneRoom ,OneRoom1},
  name: 'App',
  data(){
    return {
      showDiscount:true,
      modal : false,
      oneRoomsOri:[...data],
      oneRooms:data,
      oneroom:0,
      menu:['Home','Shop','About'],
      discountValue:30
    }
  },
  methods:{
      printSort(){
        this.oneRooms.sort((a,b)=>b.price-a.price);
      },
      sortBack(){
        this.oneRooms=[...this.oneRoomsOri];
      }
  },
  mounted(){
    setInterval(() => {
      if(this.discountValue>0){
          this.discountValue--;
      }
    }, 1000);
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


.start{
  opacity: 0;
  transition: all 1s;
}

.end{
  opacity: 1;
}

.fade-enter-from{
  opacity: 0;

}
.fade-enter-active{
  transition: all 2s;
}
.fade-enter-to{
  opacity: 1;
}
.fade-leave-from{
  opacity: 1;

}
.fade-leave-active{
  transition: all 2s;
}
.fade-leave-to{
  opacity: 0;
}
</style>

