<template>
  <div class="modal" >
    <div class="modal-content">
      <i class="bi bi-x-circle" style="font-size: xxx-large; float:right; cursor: pointer;" @click="closeModal"></i>
      <img :src="image" class="img" style=" width:500px">
      <div class="row">
        <div class="column1" >
          <i class="bi bi-arrow-bar-left buttons" style="font-size: xxx-large;"  @click="previousImg"></i>
        </div>
        <div class="column2" >
          <Thumb :image="images" />
        </div>
        <div class="column3" > 
          <i class="bi bi-arrow-bar-right buttons" style="font-size: xxx-large;" @click="nextImg"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Thumb from "../gallery/Thumb.vue"
//import "bootstrap-icons/font/bootstrap-icons.css";

export default {
  name: 'Modal',
  props: {
    image: {
      type: String,
      default: () => ''
    },
    images: {
      type: Array,
      default: () => [],
    }
  },
  components: { Thumb },

  methods: {
    closeModal() {
      this.$emit('closeModel', false)
    },
    nextImg(){
      this.$emit("nextImage")
    },
    previousImg(){
      this.$emit("previousImage")
    }
  }
}
</script>
<style scoped>
.modal {
  display: flex;
  position: absolute;
  left: 0;
  top: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0,0,0, 0.7);
}

.modal-content {
  background-color: white;
  width: 600px;
  height: 600px;
  justify-content: center;
  align-items: center;
  position: absolute;
  left: calc(50vw - 300px);
  top: calc(50vh - 300px);
}

.img {
  width: 100%;
  height: 600px;
}
.column1 {
  float: left;
  width: 5%;
  position: inherit;
}
.row{
  text-align: center;
    vertical-align: middle;
    height: 150px;
    line-height: 150px;
}
.column3 {
  float: left;
  width: 5%;
  position: inherit;
}
.column2 {
  float: left;
  width: 90%;
  top: 62.5%;
  left: 2%;
}
.row:after {
  content: "";
  display: table;
  clear: both;
}
.buttons:hover {
  border: 2px solid rgb(0, 0, 0);
  cursor: pointer;
}
</style>
