<template>
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{a}}</a>
  </div>
  <div>
    <img src="./assets/room0.jpg" class="room-img"/>
    <h4>{{products[0]}}</h4>
    <p>50 만원</p>
    <button @click="신고수[0]++">허위매물</button>
    <span> 신고수 ㅣ {{신고수[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img"/>
    <h4>{{products[1]}}</h4>
    <p>50 만원</p>
    <button @click="신고수[1]++">허위매물</button>
    <span> 신고수 ㅣ {{신고수[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img"/>
    <h4>{{products[2]}}</h4>
    <p>50 만원</p>
    <button @click="신고수[2]++">허위매물</button>
    <span> 신고수 ㅣ {{신고수[2]}}</span>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      products:['관악 원룸','강남 원룸','오산 원룸'],
      신고수:[0,0,0],
      메뉴들:['사과','바나나','오랜지']
    }
  }
};
</script>

<style>
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
}

.room-img{
 width:100%;
 margin-top:40px;
}
</style>
