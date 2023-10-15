<template>
    <div v-for="(oneRoom,i) in 원룸들" :key="i" @click="모달창열렸니=true;원룸=i">
        <OneRoom/>
    </div>
</template>

<script>
import OneRoom from './OneRoom.vue';


export default {
    name:'OneRoomList',
    props:{
        원룸들:Array
    },
    components:{
    OneRoom
}
}
</script>

<style>

</style>