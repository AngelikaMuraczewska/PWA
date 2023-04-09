<template>
<div>
  <TopNav />
  <GalleryPage></GalleryPage>
</div>
</template>

<script>

import TopNav  from '../components/navi/TopNav.vue'
import GalleryPage from './gallery.vue'
export default {
  name: 'IndexPage',
  components: { TopNav, GalleryPage},
}
</script>
<style scoped>
@import '~/assets/css/styles.css';
</style>
