<script lang="ts">
    import { ref, type Ref } from 'vue';

    const time : Ref<String> = ref("hi");
    time.value = "world";
</script>
<template>
    <h1>{{ time }}</h1>
</template>