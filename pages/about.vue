<template>
  <div>
    <h2>About</h2>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nam iusto ipsum
      et sapiente error a voluptate ipsam velit non blanditiis?
    </p>
    <p>{{ data }}</p>
  </div>
</template>

<script setup>
const { data } = await useFetch("/api/currency/GBP");
</script>

<style scoped>
</style>
