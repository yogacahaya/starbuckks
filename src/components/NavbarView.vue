<template>
  <div class="navbar">
    <!-- nav desktop -->
    <div class="nav">
      <div class="logo">
        <img src="../assets/logo.png" alt="" width="44" />
      </div>
      <ul>
        <router-link to="/">home</router-link>
        <router-link to="/products">products</router-link>
      </ul>
    </div>
    <!-- nav mobile -->

    <div class="bar">
      <span @click="add()" class="material-symbols-outlined menu"> menu </span>
      <div class="nav1" :class="{ active: unActive }">
        <span @click="remove()" class="material-symbols-outlined move"> close </span>
        <ul>
          <router-link to="/">home</router-link>
          <router-link to="/products">products</router-link>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavbarView",
  data() {
    return {
      unActive: false,
    };
  },
  methods: {
    add() {
      this.unActive = true;
    },
    remove(){
        this.unActive = false
    }
  },
};
</script>
