<template>
  <div class="home">
    <NavbarView />
    <HeroView/>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarView from '@/components/NavbarView.vue'
import HeroView from '@/components/HeroView.vue'

export default {
  name: 'HomeView',
  components: {
    NavbarView,
    HeroView
  }
}
</script>
