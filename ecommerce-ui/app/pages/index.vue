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
      <v-col cols="12" md="3" v-for="item in 5" :key="item">
        <v-card elevation="5">
          <v-img
          height="150"
          src="https://placehold.co/600x400?text=Product"
          cover
          >
        </v-img>

        <v-card-title>Mouse</v-card-title>
        <v-caed-text>1500</v-caed-text>
        <c-card-action>
          <v-btn color="black" variant="flat" block>Add to Cart</v-btn>
        </c-card-action>
        </v-card>
      </v-col>
    </v-row>

  </v-container>
</template>

<script lang="ts" setup>

</script>

<style>

</style>