<template>
  <div class="obj">
    <h2>Product</h2>

    <div class="container">
      
      <input v-model="search" type="text" placeholder="Search..." @keyup="searchFood" />
      <div class="search"><span class="material-symbols-outlined">
search
</span></div>
    </div>

    <div class="cardss">
      <div class="card" v-for="product in products" :key="product.id">
        <CardView :product="product" />
      </div>
    </div>
  </div>
</template>

<script>
import CardView from "@/card/CardView.vue";
import axios from "axios";

export default {
  name: "ProductList",
  components: {
    CardView,
  },
  data() {
    return {
      products: [],
      search: '',
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
    },
    searchFood(){
      axios
      .get("http://localhost:3000/products?q="+this.search)
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
    }
  },
  mounted() {
    axios
      .get("http://localhost:3000/products")
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style >
.obj {
  margin-top: 75px;
  /* margin-left: 145px; */
}
.obj h2 {
  font-weight: 400;
}
.container{
  display: flex;
  margin-left: 45px;
}
</style>