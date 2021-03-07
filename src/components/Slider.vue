<template>
  <div class="flex flex-wrap relative mb-72">
    <div class="absolute overflow-x-hidden" v-for="(slider, index) in sliderimage" :key="slider">
      <transition name="fade">
        <img v-if="currentslider === index" :src="slider.url" :alt="slider.alt" class="w-full my-3" style="height:250px">
      </transition>
    </div>
    <div class="w-full h-full absolute mt-60">
      <div class="w-full flex justify-center">
        <div v-for="(slider, index) in sliderimage" @click="isactive(index)" :key="slider" :class="currentslider == index ? 'bg-gray-700':'bg-gray-300'" class="mx-2 rounded-full bg-black w-4 h-4"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    isactive(index){
      this.currentslider = index
    }
  },
  mounted(){
    this.intervals = setInterval(() => {
        this.currentslider = this.currentslider === 2? 0:this.currentslider+1
    }, 3000);
  },
  beforeUnmount(){
    clearInterval(this.intervals)
  },
  data(){
    return {
      intervals:'',
      currentslider: 0, 
      sliderimage: [
        {url:require('../assets/images/promo2.jpg'), alt:'Promo 1'},
        {url:require('../assets/images/promo3.jpg'), alt:'Promo 2'},
        {url:require('../assets/images/promo1.jpg'), alt:'Promo 3'}
      ]
    }
  }
}
</script>

<style>

.fade-enter-active, .fade-leave-active {
    transition: all 1s ease;
}

.fade-enter-from {
    opacity: 0;
    transform: translateX(-100%);
}

.fade-leave-to {
    opacity: 0;
    transform: translateX(100%);
}

</style>