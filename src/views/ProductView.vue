<template>
  <div>
    <NavbarView/>
    <ProductList/>
  </div>
</template> 

<script>

import NavbarView from '@/components/NavbarView.vue'
import ProductList from '@/components/ProductList.vue'

export default {
name: 'ProductVIew',
components: {
    NavbarView,
    ProductList
  }
}
</script>

<style>

</style>