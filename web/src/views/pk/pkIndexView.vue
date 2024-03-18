<template>
<ContentField>
    <PlayGround v-if="$store.state.pk.status==='playing'"></PlayGround>
    <MatchGround v-if="$store.state.pk.status==='matching'"></MatchGround>
</ContentField>
</template>
<script>
import PlayGround from '../../components/PlayGround.vue'
import MatchGround from '../../components/MatchGround.vue'
import { onMounted, onUnmounted } from 'vue';
import { useStore } from 'vuex';


export default{
    components:{
        
        PlayGround,
        MatchGround
    },
    setup(){
        const store = useStore();
        const socketUrl = `ws://127.0.0.1:3000/websocket/${store.state.user.token}/`;

        let socket = null;
        onMounted(()=>{
            socket = new WebSocket(socketUrl);

            socket.onopen = () => {
                console.log('connected!');
            }

            socket.onmessage = msg => {
                const data = JSON.parse(msg.data);
                console.log(data);
            }

            socket.onclose = () => {
                console.log("disconnected!");
            }

        });

        onUnmounted(() => {
            socket.close();
            // store.commit("updateStatus", "matching");
        })

    }

}
</script>
<style scoped>

</style>