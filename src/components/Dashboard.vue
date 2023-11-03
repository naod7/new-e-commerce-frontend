<script setup>
  import {ref} from "vue"
  import data from "@/products.json"
  import {defineProps} from 'vue'
  import ProductCard from "@/components/ProductCard.vue"

  const {product, addToCart} = defineProps(['product', 'addToCart'])

  const products = ref(data)
</script>

<template>
    <v-container fluid>
      <v-card
        color="#3853D8"
        height="150px"
        tile
        flat
        class="d-flex align-center justify-center"
        dark
      >
        <v-row>
          <v-col cols="12" sm="12">
            <h4 class="text-center">MEN'S LIFESTYLE SHOES</h4>
          </v-col>
          <v-col cols="12" sm="12">
            <v-breadcrumbs :items="items" class="justify-center mt-n7" dark>
              <template v-slot:divider>
                <v-icon color="#7C92FE">mdi-chevron-right</v-icon>
              </template>
            </v-breadcrumbs>
          </v-col>
        </v-row>
      </v-card>
      <v-card tile class="mx-16 mt-n10 card1" color="white">
        <v-row>
          <v-col cols="12" sm="8" class="pr-0">
            <v-card height="250px" tile flat color="#3890D8">
              <v-row>
                <v-col cols="12" sm="4" class="pl-8 pt-5">
                  <v-btn color="black" dark class="withoutupercase" small tile>
                    new
                  </v-btn>
                  <h6 class="white--text mt-8">Mens Plaid Hoodie</h6>

                  <v-btn
                    rounded
                    color="#4C9CDB"
                    dark
                    class="withoutupercase px-8 mt-10"
                  >
                    More Info
                  </v-btn>
                </v-col>
                <v-col cols="12" sm="8">
                  <!---<v-img
                    src="@/assets/26869.Lg.jpg"
                    max-height="400"
                    max-width="400"
                    contain
                    class="mt-n6"
                  ></v-img>
                  <img src="https://image.doba.com/dg9-ojvZrILZDQqd/mens-plaid-hoodies-fleece-sweater.webp" height="250"
                  width="400"/>--->
                  <v-img src="https://image.doba.com/dg9-ojvZrILZDQqd/mens-plaid-hoodies-fleece-sweater.webp">

                  </v-img>
                </v-col>
              </v-row>
            </v-card>
          </v-col>
          <v-col cols="12" sm="4" class="pl-0">
            <v-card height="250px" tile flat color="#6857E1">
              <v-row>
                <v-col cols="12" sm="6" class="pl-8 pt-5">
                  <v-btn color="black" dark class="withoutupercase" small tile>
                    new
                  </v-btn>
                  <h6 class="white--text mt-8">DOWN JACKET</h6>
                  <h3 class="white--text mt-5">Sale Collection 2015</h3>
                  <v-btn
                    rounded
                    color="#8375E7"
                    dark
                    class="withoutupercase px-8 mt-3"
                  >
                    More Info
                  </v-btn>
                </v-col>
                <v-col cols="12" sm="6">
                  <!--<v-img
                    src="https://image.doba.com/dg9-MReSVKhvrQvi/space-coast-shirt---mens-shirt.webp"
                    max-height="400"
                    max-width="420"
                    contain
                    class="mt-n2"
                  ></v-img>---->
                  <img src="https://image.doba.com/dg9-gYDvymJfpoqr/men-windbreaker-military-field-jackets-outerwear-mens-winter-autumn-waterproof-flight-pilot-coat-hoodie-men-hunting-army-clothes.webp" height="250"
                  width="250"/>
                </v-col>
              </v-row>
            </v-card>
          </v-col>
        </v-row>
        <v-row>

          <v-divider horizontal ></v-divider>
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


        </v-row>
      </v-card>
    </v-container>
  </template>


  <style>
  .container {
    padding: 0px !important;
  }
  .v-btn.withoutupercase {
    text-decoration: none;
  }
  .v-chip.v-size--default {
    border-radius: 50px !important;
    font-size: 14px !important;
    height: 40px !important;
    width: 40px !important;
  }
  .v-card--reveal {
    align-items: center;
    bottom: 0;
    justify-content: center;
    opacity: 0.5;
    position: absolute;
    width: 100%;
  }
  .card1 {
    z-index: 10;
  }
  .card2 {
    z-index: 1;
  }
  </style>