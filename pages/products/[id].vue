<template>
  <div>
    <Head>
      <TitLe>Nuxt | {{product.title}}</TitLe>
      <Meta name="description" :content="product.content"></Meta>
    </Head>
    <ProductDetails :product="product"></ProductDetails>
  </div>
</template>

<script setup>
const { id } = useRoute().params

// fetch the product
const url = 'https://fakestoreapi.com/products/'+id
const { data: product }  =  await useFetch(url,{key: id})

// useHead({
//   title: 'Nuxt Dojo | Merch',
//   meta: [
//     {name: 'description', content: 'Nuxt 3 Merch'}
//   ]
// })

if(!product.value){
  throw createError({statusCode: 404, statusMessage: 'Product not found', fatal: true});
}

definePageMeta({
  layout: 'products'
})

</script>

<style>

</style>