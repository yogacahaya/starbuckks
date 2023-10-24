<template>
  <div class="rows">
    <div class="details">
      <img :src="product.gambar" alt="" />
    </div>
    <div class="detail-title">
      <h2>{{ product.nama }}</h2>
      <hr />
      <h4>
        Harga: <strong>Rp. {{ product.harga }}</strong>
      </h4>
      <form>
        <div class="form" v-on:submit.prevent>
          <label for="jumlah_order">Jumlah Order</label>
        </div>
        <input type="number" v-model="pesan.jumlah_order"/>
      </form>
      <div class="btn-form">
        <button type="submit" @click="pemesanan">Bayar</button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Notiflix from 'notiflix';

export default {
  name: "FoodView",
  data() {
    return {
      product: [],
      pesan: []
    };
  },
  methods: {
    setProducts(data) {
      this.product = data;
    },
    pemesanan(){
       this.pesan = this.product;
       axios
       .post("http://localhost:3000/keranjang", this.pesan)
       .then(() => {
        Notiflix.Notify.success('Pemesanan berhasil')
       })
       .catch((err) => console.log(err))
    }
  },
  mounted() {
    axios
      .get("http://localhost:3000/products/" + this.$route.params.id)
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
.details img {
  width: 225px;
}
.rows {
  /* display: flex; */
  margin-top: 45px;
}
.detail-title {
  margin-top: 45px;
}
.btn-form {
  margin-top: 12px;
  float: right;
}
.btn-form button {
  background: #2acc83;
  width: 64px;
  height: 32px;
  color: #fff;
  border-radius: 8px;
}
</style>