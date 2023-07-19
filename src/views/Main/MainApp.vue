<template>
    <div>
        <Clock/>
    </div>
</template>

<script setup>
import { mainStore } from "@/store";

import Clock from "@/components/Clock/index.vue";

const store = mainStore();

</script>

<style lang="scss" scoped>
</style>