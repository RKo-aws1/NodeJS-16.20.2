<script setup lang="ts">
  import { ref } from 'vue';

  const now = new Date();
  const nowStr = now.toLocaleTimeString();
  let timeStr = nowStr;
  const timeStrRef = ref(nowStr);
  function changeTime() {
    const newNow = new Date();
    const newNowStr = newNow.toLocaleTimeString();
    timeStr = newNowStr;
    timeStrRef.value = newNowStr;
  }
  setInterval(changeTime, 1000);
</script>

<template>
  <div>
    <p>Current Time: {{ timeStr }}</p>
    <p>Current Time (ref): {{ timeStrRef }}</p>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
