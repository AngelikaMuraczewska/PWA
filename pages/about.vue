<template>
<div>
  <TopNav />
  <h1>O nas</h1>
  <button @click="showInfo">Kliknij mnie</button>
</div>
</template>

<script>
import TopNav  from '../components/navi/TopNav.vue'
export default {
  name: 'IndexPage',
  components: { TopNav },
  methods:{
    showInfo: ()=>{
        console.log('witaj w konsoli')
        alert('witaj')
    }
  }
}
</script>
