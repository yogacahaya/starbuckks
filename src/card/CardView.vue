<template>
    <div class="banner">
      <div class="crad">
        <img :src="product.gambar" alt="">
        <div class="title-crad">
          <h2>{{ product.nama }}</h2>
          <span>{{ product.harga }}</span>
        </div>
        <div class="btn-crad">
          <button><router-link :to="'/products/'+ product.id " style="color: #fff; font-weight: 600;">order</router-link></button>
        </div>
      </div>
    </div>
</template>

<script>
export default {
    name: 'CardView',
    props: ['product']
}
</script>

<style>
.crad img{
  width: 125px;
  margin-left: 45px;
}
.crad{
  width: 245px;
  height: 375px;
  border: 1px solid black;
  border-radius: 8px;
  background: #fff;
  box-shadow: hsla(0, 3%, 31%, 0);
}
.title-crad{
  text-align: center;
}
.btn-crad{
  margin-left: 95px;
}
.btn-crad button{
  width: 64px;
  height: 32px;
  color: #fff;
  background: #2acc83;
  border-radius: 8px;
}
</style>