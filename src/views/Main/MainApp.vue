<template>
  <div >
    <div class="time">
        <div class="text">
            <!-- 时间 -->
            <span>
                {{ currentTime.hour }}:{{ currentTime.minute }}:{{ currentTime.second }}
            </span>
        </div>
        <div class="data">
            <!-- 日期 -->
            <span>{{ currentTime.year }}年</span>
            <span>{{ currentTime.month }}月</span>
            <span>{{ currentTime.day }}日&nbsp;</span>
            <span>{{ currentTime.weekday }}</span>
        </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";
import { getCurrentTime } from "@/utils/getTime";
import { mainStore } from "@/store";

const store = mainStore();

const currentTime = ref({});
const timeInterval = ref(null);

onMounted(() => {
  timeInterval.value = setInterval(() => {
    currentTime.value = getCurrentTime();
  }, 1000);
});

onBeforeUnmount(() => {
  clearInterval(timeInterval.value);
});
</script>

<style lang="scss" scoped>
.time {
    font-size: 2rem;
    text-align: center;
    // 日期
    .date {
        text-overflow: ellipsis;
        overflow-x: hidden;
        white-space: nowrap;
    }
    // 数字时间
    .text {
        margin-top: 10px;
        font-size: 8rem;
        letter-spacing: 2px;
        // font-family: "UnidreamLED";
    }
}
</style>