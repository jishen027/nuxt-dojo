<template>
  <div>
    <ProductDetails :product="product"></ProductDetails>
  </div>
</template>

<script setup>
const { id } = useRoute().params

// fetch the product
const url = 'https://fakestoreapi.com/products/'+id
const { data: product }  =  await useFetch(url,{key: id});

definePageMeta({
  layout: 'products'
})

</script>

<style>

</style>