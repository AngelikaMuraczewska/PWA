<template>
  <div class="nav">
    <NuxtLink class="nav-item" to="/">Strona domowa</NuxtLink>
    <NuxtLink class="nav-item" to="/about">O nas</NuxtLink>
    <NuxtLink class="nav-item" to="/gallery">Galeria</NuxtLink>
  </div>
</template>

<script>
export default {
  name: 'NavTop',
}
</script>
<style scoped>
.nav {
  display: flex;
  width: 100vw;
  color: white;
  height: 50px;
  background-color: dodgerblue;
  justify-content: center;
  align-items: center;
}

.item{
    max-height:100px;
    min-height:100px;
    max-width:100px;
    min-width: 100px;
    border:solid blue;
}
.item2{
    flex-direction: column;
    display: flex;
}
.left-nav{
    font-size: 14px;
    max-height:100px;
    min-height:100px;
    max-width:50px;
    min-width: 100px;
}

.nav-item {
  padding: 0 10px;
  text-decoration: none;
  color: white;
}

.nuxt-link-exact-active,.nav-item:hover {
  color: brown;
}
</style>
