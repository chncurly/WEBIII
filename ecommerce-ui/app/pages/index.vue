<template>
  <v-container>

    <v-app-bar color="grey"></v-app-bar>

    <v-row>
      <v-col>
        <h1>Products</h1>
          <p>Browse Products, add to cart and checkout</p>
      </v-col>
    </v-row>

    <v-row>
      <v-col cols="12" md="3" v-for="item in products" :key="item">
        <v-card elevation="5">
          <v-img
          height="150"
          src="https://placehold.co/600x400?text=Product"
          cover
          >
        </v-img>

        <v-card-title>{{ item.name }}</v-card-title>
        <v-caed-text>{{ item.price }}</v-caed-text>
        <c-card-action>
          <v-btn color="black" variant="flat" block>Add to Cart</v-btn>
        </c-card-action>
        </v-card>
      </v-col>
    </v-row>

  </v-container>
</template>

<script lang="ts" setup>
//@ts-nocheck
const config = useRuntimeConfig();
const products = ref([])

// fetch preloadRouteComponents
async function fetchProducts () {
  try{
    const response = await $fetch("/api/products", {
      baseURL: "http://localhost:1337",
    });
    console.log(response.data);
    products.value = response.data
  }catch (err){
    console.error("Failed to load Products")
  }
}
// add to cart 

// submit order 

// remove from cart 

onMounted(() => {
  fetchProducts()
})

</script>

<style>

</style>