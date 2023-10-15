<template>
    <div v-for="(oneRoom,i) in 원룸들" :key="i" >
        <OneRoom :oneRoom="oneRoom" @click="모달창열렸니=true/>
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