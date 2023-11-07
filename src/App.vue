<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">

      <nav>
        <li>
          <RouterLink to="/">Home</RouterLink>
        </li>
        <li>
          <RouterLink to="/about">About</RouterLink>
        </li>
        <li>
          <RouterLink to="/contact">Contact</RouterLink>
        </li>
        <li>
          <RouterLink to="/products">Products</RouterLink>
        </li>
      </nav>
    </div>
  </header>
<div class="test">
  <RouterView />
</div>
</template>

<style scoped>
.test{
  padding-top: 5%;
}
nav {
  position: fixed;
  background-color: #000000;
  padding: 10px;
  width: 100%;
}

nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

nav li {
  display: inline;
  margin-right: 20px;
}

nav a {
  text-decoration: none;
  color: #fff;
  font-weight: bold;
}

nav a:hover {
  color: rgb(0, 68, 255);
}
</style>