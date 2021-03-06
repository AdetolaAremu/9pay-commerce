<template>
  
  <input type="text" v-model="search" placeholder="Search me">

  <button @click="sortedArray(nameofservice)">SORT</button>

  <section class="grid grid-cols-4 text-center font-semibold ml-9">
    <div class="w-max bg-white my-4 shadow-md rounded-md" v-for="image in filteredList" :key="image">
      <a href="">
        <img :src="image.url" class="h-44 w-56">
        <div class="py-5">{{ image.nameofservice }}</div>
      </a>   
    </div>
  </section>
</template>

<script>

export default {
  methods: {
    sortedArray(){
    this.images.sort((a, b) => (a.nameofservice > b.nameofservice) ? 1 : -1)
  } 
  },
  computed: {
    filteredList() {
      return this.images.filter(image => {
        return image.nameofservice.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  },
  data(){
    return {
      search: '',
      images: [
        {url:require('./assets/images/agric11.jpg'), nameofservice:'Agric Foods', type:'seller'},
        {url:require('./assets/images/aquaculture-fish-farming17.jpg'), nameofservice:'Fries and Fishes', type:'seller'},
        {url:require('./assets/images/bread28.jpg'), nameofservice:'Bola Bakery', type:'seller'},
        {url:require('./assets/images/automobileservice1.jpg'), nameofservice:'Dannie & Sons Auto', type:'provider'},
        {url:require('./assets/images/courier5.jpg'), nameofservice:'The Courier', type:'provider'},
        {url:require('./assets/images/cvservice3.jpg'), nameofservice:'The CV Guru', type:'provider'},
        {url:require('./assets/images/dental6.png'), nameofservice:'Mallam Dental', type:'provider'},
        {url:require('./assets/images/designer8.jpg'), nameofservice:'Vivid Designs', type:'provider'},
        {url:require('./assets/images/Electronics26.jpg'), nameofservice:'Electronic Shopa', type:'provider'},
        {url:require('./assets/images/fabric22.jpg'), nameofservice:'Fabric Store', type:'provider'},
        {url:require('./assets/images/fashion-designer9.jpg'), nameofservice:'Mallam Fashion', type:'provider'},
        {url:require('./assets/images/fedex-truck-service4.jpg'), nameofservice:'Fedex Logistics', type:'provider'},
        {url:require('./assets/images/GIG7.jpg'), nameofservice:'Good Is Good Logistics', type:'provider'},
        {url:require('./assets/images/Amala.jpg'), nameofservice:'Amala Skye', type:'seller'},
        {url:require('./assets/images/foods.jpg'), nameofservice:'Food Paradise', type:'seller'},
        {url:require('./assets/images/interior16.jpg'), nameofservice:'Beautify', type:'provider'},
        {url:require('./assets/images/kitchenconfec14.jpg'), nameofservice:'Regalo Kitchen', type:'seller'},
        {url:require('./assets/images/magic-mug24.jpg'), nameofservice:'Magic Prints', type:'provider'},
        {url:require('./assets/images/mobilephones10.png'), nameofservice:'Phones and Accessories', type:'seller'},
        {url:require('./assets/images/paint18.jpg'), nameofservice:'We Paint', type:'provider'},
        {url:require('./assets/images/rice19.jpg'), nameofservice:'Elephant Rice', type:'seller'},
        {url:require('./assets/images/sellcomp25.jpg'), nameofservice:'Our Pikin Computer', type:'seller'},
        {url:require('./assets/images/confection.jpg'), nameofservice:'Confec House', type:'seller'},
        {url:require('./assets/images/shoprite27.png'), nameofservice:'ShopRite', type:'seller'},
        {url:require('./assets/images/sundry20.jpg'), nameofservice:'Sundry Foods', type:'seller'},
        {url:require('./assets/images/supply15.jpg'), nameofservice:'SupplyAllOva', type:'provider'},
        {url:require('./assets/images/tshirt23.jpg'), nameofservice:'T-shirt Prints', type:'provider'},
      ]
    }
  }
}
</script>

<style>

</style>