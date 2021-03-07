<template>
  <Appheader />
  <Slider />
  <ImageFilters />
  <Appfooter />
</template>

<script>
import Appheader from './components/Appheader';
import Slider from './components/Slider';
import ImageFilters from './components/ImageFilters';
import Appfooter from './components/Appfooter';
export default {
  components: { Appheader, Slider, ImageFilters, Appfooter },
}
</script>

<style>
.active {
  color: red;
  border-bottom: 1px solid red;
}
</style>