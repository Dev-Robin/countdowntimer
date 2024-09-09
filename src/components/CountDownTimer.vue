<script setup lang="ts">
    import { ref, type Ref } from 'vue';

    const time : Ref<String> = ref("hi");

    const countDownTime : number = new Date("10 september 2024 17:00:00").getTime();
    setInterval(() => {
        const dateNow : number = new Date().getTime();
        
        let distance = countDownTime - dateNow;

        let days = Math.floor(distance / (1000 * 60 * 60 * 24));
        let hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        let minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        let seconds = Math.floor((distance % (1000 * 60)) / 1000);
        
        time.value = `${days}d:${hours}h:${minutes}m:${seconds}s`;
    }, 1000); 
</script>
<template>
    <h1>Countdown until Satisfactory 1.0 release:</h1><br>
    <h1>{{ time }}</h1>
</template>
<style scoped>
    h1 {
        text-align: center;
    }
</style>