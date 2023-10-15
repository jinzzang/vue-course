<template>
    <div v-for="(oneRoom,i) in 원룸들" :key="i" @click="모달창열렸니=true;원룸=i">
        <img :src="oneRoom.image" class="room-img"/>
        <h4>{{oneRoom.title}} </h4>
        <p>{{oneRoom.price}} 원</p>
    </div>
</template>

<script>
export default {
    name:'OneRoomList',
    props:{
        oneRoom:Object
    }
}
</script>

<style>

</style>