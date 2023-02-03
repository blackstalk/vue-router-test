<template>
    <ul v-for="product in products">
        <li>
            <h3>{{ product.title }}</h3>
            <p>{{ product.description }}</p>
            <img v-bind:src="product.thumbnail" />
            <hr />
        </li>
    </ul>
</template>

<script>
import axios from 'axios'
import { ref, onMounted } from 'vue';

export default {
    name: "ProductsList",
    setup() {
        const products = ref([]);
        onMounted(async () => {
            const { data } = await axios.get("https://dummyjson.com/products");
            console.log(data);
            products.value = data.products
        })
        return {
            products
        }
    },
}
</script>
