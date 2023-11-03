<script setup>
import {ref, defineProps} from "vue"
  import data from "@/products.json"
  import ProductCard from "@/components/ProductCard.vue"

  const {addToCart} = defineProps(['addToCart'])
  const products = ref(data)

</script>



<template>
    <h1 style="align-tex:center">Products</h1>
    <v-col cols="9" class="mt-n3">
        <v-row>
            <ProductCard
            v-for="(product, i) in products"
            :key="i"
            :product="product"
            :class="product.class"
            :addToCart="addToCart"
            />
        </v-row>


    </v-col>

</template>