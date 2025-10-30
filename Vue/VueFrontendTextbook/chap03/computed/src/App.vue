<script setup lang="ts">
  import {ref, computed} from "vue";
  
  const radiusInit = Math.round(Math.random() * 10);
  const PI = ref(3.14);
  const radius = ref(radiusInit);

  const area =computed(
    (): number => {
      return radius.value * radius.value * PI.value;
    }
  );

  setInterval(
    (): void => {
      radius.value = Math.round(Math.random() * 10);
    }, 1000
  );

</script>

<template>
  <div id="app">
    <p>
      The area of a circle with Radius {{ radius }} is {{ area }}
    </p>
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
