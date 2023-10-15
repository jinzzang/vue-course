<template>
    <div>
        <img :src="oneRoom.image" class="room-img"/>
        <h4 @click="send()">{{oneRoom.title}} </h4>
        <p>{{oneRoom.price}} 원</p>
    </div>
</template>

<script>
export default {
    name:'OneRoom1',
    props:{
        oneRoom:Object
    },
    methos:{
        send(){
            this.$emit('openModal',this.oneRoom.id);
        }
    }
}
</script>

<style>

</style>