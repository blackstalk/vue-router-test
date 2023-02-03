<template>
  <div class="about">
    <h1>This is the products page using axios async await</h1>
    <ProductsList />
  </div>
</template>

<script>
import ProductsList from "@/components/ProductsList.vue";
export default {
  name: "ProductsView",
  components: {
    ProductsList,
  },
};
</script>
