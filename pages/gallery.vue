<template>
  <div>
    <TopNav/>
    <BigImg :image="img" @rm="runModal($event)"/>
    <Thumb :images="items" @selectedImg="showImg($event)"/>
    <Modal v-show="showModal" :image="img"       
      @nextImage="nextImg($event)"
      @closeModel="runModal($event)"
      @previousImage="previousImg($event)"
      @showImage="showImg($event)"/>
  </div>
</template>

<script>
import TopNav from '../components/navi/TopNav.vue'
import Thumb from '../components/gallery/Thumb.vue'
import BigImg from "~/components/gallery/BigImg.vue";
import Modal from "~/components/modals/modal.vue";

export default {
  name: 'GalleryPage',
  components: {BigImg, TopNav, Thumb, Modal},
  data() {
    return {
      items: [
        'https://img.freepik.com/free-photo/dark-photo-studio-curly-middle-aged-man-is-posing-with-guitar-photographer_613910-1762.jpg?w=740&t=st=1679834037~exp=1679834637~hmac=3b432e14d04959b67c113f52fbcca878496a4e079a6b41ad66b47fc3ac006322',
        'https://img.freepik.com/free-photo/musician-plays-acoustic-guitar_169016-3935.jpg?w=740&t=st=1679834127~exp=1679834727~hmac=693b9cf1f81eaf4c1eab266a6c3afe3a6383a1aacf0116335c700175e8791788',
        'https://img.freepik.com/free-photo/man-holding-acoustic-guitar-his-hands-copy-space_169016-10978.jpg?w=1380&t=st=1679834182~exp=1679834782~hmac=ac79da3a46bbfe793d29e7f0af7eb9778f5a067e7d5f1430db09996f84d204a1'
      ],

      img: 'https://img.freepik.com/free-photo/acoustic-guitar-close-up-beautiful-colored-background_169016-3530.jpg?w=740&t=st=1679831837~exp=1679832437~hmac=0f6916d41549c974a53d487f8be077c6e042aceec5efa45ea5e9547308851df6',
      selectedIndex: 0,
      showModal : false
    }
  },

  methods: {
    nextImg(){
      this.selectedIndex = (this.selectedIndex + 1) % this.items.length
      this.img = this.items[this.selectedIndex]
    },
    previousImg(){
      if(this.selectedIndex==0){
        this.selectedIndex= this.items.length-1}
      else{ 
        this.selectedIndex = (this.selectedIndex - 1) % this.items.length}  
      this.img = this.items[this.selectedIndex]
    },
    showImg(selectedImg) {
      this.img = selectedImg.url;
      this.selectedIndex = selectedImg.index;
    },
    runModal(e) {
      console.log(e)
      this.showModal = e
    }
  }
}
</script>
