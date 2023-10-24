<template>
    <div class="blok">
        <div class="hero">
    <!-- img -->
    <div class="hero-img">
      <div class="imgBox" v-if="page === 'image1'">
        <img :src="image1" alt="" width="356" />
      </div>

      <div class="imgBox" v-if="page === 'image2'">
        <img :src="image2" alt="" width="356" />
      </div>
    </div>
    <!-- title -->
    <div class="icon">
      <img @click="naviGate('image1')" :src="image1" alt="" width="64" />
      <img @click="naviGate('image2')" :src="image2" alt="" width="64" />
    </div>
    <div class="title-hero">
      <span>STARBUCKS</span>
      <h2>MVP COLLECTION</h2>
    </div>

    <div class="best">
      <div class="sub">
        <span>Best <strong>Product</strong></span>
      </div>
      <div class="view">
        <button><router-link to="/products" style="color: #fff;">View</router-link></button>
      </div>
    </div>
    
  </div>
  <div class="cardss">
        <div class="card" v-for="product in products" :key="product.id">
      <CardView :product="product"/>
    </div>
    </div>
    </div>
  
</template>

<script>
import CardView from "@/card/CardView.vue";
import axios from "axios";

export default {
  name: "HeroView",
  components: {
    CardView,
  },
  data() {
    return {
      image1:
        "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiIYsHRQUca_BJahx4QybkcACy3NtvAd614TPSxdAYw0N1gx8JeXaRvyZFSfBl3qBI9cr83dXaJ52ypTqm_ZahAZdrBUWfNgLa0tce7U-lzGx0EqSeCoj0Zj0DpVuXdvUZX_JwiGSGR4da5N_T2szl-pRj-dsQsOylPZB1D0HFYG8XTIISt1KVFBBjCsGjD/s899/77325-frappuccino-drink-chocolate-starbucks-matcha-white.png",
      image2:
        "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEifZbLryErcL8nJkeomV82NGnTqQuoXLQPOfNGN9yyhV_9e1ZIra_HqjgHjVwVZKXktihE3Xws7KoRlr-NWCtZjB5SLPr3N4hSOoNfH1xZRfDrA1IB2JZd58S5zl3tG5WSPLYyq3vAOH7F8Mu4qj-T_hUvAowUgColFKlM5Bcsp3iTDa7P3sOwDeubds8AB/s865/62115-tea-coffee-drink-starbucks-latte-free-download-image.png",
      page: "image1",
      products: [],
    };
  },
  methods: {
    naviGate(page) {
      this.page = page;
    },
    setProduct(data) {
      this.products = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/best-product")
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
.hero-img {
  margin-left: 475px;
}
.hero {
  margin-top: 45px;
}
.icon {
  float: right;
  margin-top: -375px;
  margin-right: 424px;
  display: grid;
}
.title-hero {
  text-align: center;
}
.title-hero span {
  font-weight: 400;
  font-size: 24px;
  font-family: "anton";
}
.title-hero h2 {
  font-weight: 600;
  font-size: 64px;
  margin-top: -2px;
  font-family: "montserrat";
}
.best {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.sub {
  margin-left: 45px;
}
.sub span {
  font-size: 24px;
}
.view button {
  width: 85px;
  height: 32px;
  background: #42b983;
  color: #fff;
  border-radius: 8px;
}
.cardss{
    display: grid;
    margin-top: 25px;
    grid-template-columns: repeat(3);
}
.card {
  margin-left: 145px;
  margin-top: 22px;
}
@media screen and (max-width: 476px) {
  .hero-img {
    margin-left: -15px;
  }
  .hero-img img {
    width: 325px;
  }
  .hero {
    margin-top: 74px;
  }
  .title-hero h2 {
    font-size: 44px;
  }
  .nav {
    margin-top: -125px;
  }
  .nav1 {
    margin-top: -32px;
    position: fixed;
    margin-left: -275px;
    background: hsl(0, 0%, 100%);
    width: 260px;
    height: 100vh;
  }
  .nav1 a {
    font-weight: bold;
    color: #000;
    margin-left: 12px;
    display: grid;
  }
  .menu {
    margin-top: -45px;
  }
  .bar span {
    cursor: pointer;
    float: right;
  }
  .move {
    cursor: pointer;
    float: left;
  }
  .active {
    margin-left: 25px;
    transition: 0.3s cubic-bezier(0.075, 0.82, 0.165, 1);
  }
  .nav1 a.router-link-exact-active {
    color: #42b983;
  }
  .sub {
    margin-left: 15px;
  }
  .sub span {
    font-size: 12px;
  }
  .view button {
    width: 44px;
    height: 32px;
    font-size: 12px;
  }
  .crad img{
    width: 94px;
    margin-left: 62px;
  }
  .crad{
    width: 245px;
    height: 325px;
   
  }
  .btn-crad{
    margin-left: 95px;
    margin-top: 12px;
  }
  .cardss{
    display: grid;
    grid-template-columns: repeat(3);
  }
  .card{
    margin-left: 25px;
    margin-top: 22px;
  }
}
</style>