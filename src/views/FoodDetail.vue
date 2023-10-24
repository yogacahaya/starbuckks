<template>
  <div class="food-detail">
    <NavbarView/>
    <FoodViewVue/>
  </div>
</template>

<script>
import NavbarView from '@/components/NavbarView.vue'
import FoodViewVue from '@/components/FoodView.vue';

export default {
    name: 'FoodDetail',
    components: {
        NavbarView,
        FoodViewVue
    }
}
</script>

<style>

</style>