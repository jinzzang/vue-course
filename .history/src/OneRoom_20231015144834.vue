<template>
    <h1>{{i}}</h1>
    <img :src="oneRoom.image" class="room-img"/>
    <h4>{{oneRoom.title}} </h4>
    <p>{{oneRoom.price}} 원</p>
</template>

<script>
export default {
    name:'OneRoom',
    props:{
        oneRoom:Object
    }
}
</script>

<style>

</style>