<script setup>
import {defineProps, ref} from 'vue'

const {product, addToCart} = defineProps(['product', 'addToCart'])


const quantity = ref(0)
</script>


<template>

        <v-col
        cols="12"
        sm="4"


    >
        <v-hover v-slot:default="{ hover }">
        <v-card height="300" align="center" flat outlined tile>
            <!---<v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="black" small dark>{{ product.sold }}</v-btn>
            </v-card-actions>---->
            <v-img
            :src="product.image"
            width="200"
            height="200"
            contain
            ></v-img>
            <v-card-text class="mt-n4">
            <strong :class="hover ? 'red--text' : 'black--text'">{{
                product.title
            }}</strong>
            </v-card-text>
            <div class="row">
                <div class="cell">
                  <label>Quantity:</label>
                </div>
                <div class="cell">
                  <input type="number"  v-model.number="quantity">
                </div>
            </div>

            <v-expand-transition>
            <div

                class="
                d-flex
                transition-fast-in-fast-out
                blue
                v-card--reveal
                display-3
                white--text
                "
                style="height: 100%"
            >
                <v-btn rounded color="white" @click="addToCart(product.title, quantity)">
                <v-icon>mdi-cart-outlined</v-icon>
                Add To Cart
                </v-btn>
                <v-btn fab small color="white" class="ml-2">
                <v-icon color="black">mdi-heart-outline</v-icon>
                </v-btn>
            </div>
            </v-expand-transition>
        </v-card>
        </v-hover>
    </v-col>

</template>