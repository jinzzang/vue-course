<template>
  <div>
    <h4>{{product[0]}}</h4>
    <p>50 만원</p>
    <button @click="신고수[0]"></button>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
    
  },
  data(){
    return {
      product:['관악 원룸','강남 원룸','오산 원룸'],
      신고수:[0,0,0]
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
</style>
