<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-decoration: none;
  list-style: none;
  box-sizing: border-box;
  font-family: 'Anton', sans-serif;
font-family: 'Montserrat', sans-serif;
font-family: 'Roboto', sans-serif;
}

.nav {
  position: fixed;
  top: 0;
  display: flex;
  padding: 30px;
}

.nav a {
  font-weight: bold;
  color: #000;
  margin-left: 12px;
}

.nav a.router-link-exact-active {
  color: #42b983;
}
.nav1{
  position: absolute;
  margin-top: -577px;
}

</style>
