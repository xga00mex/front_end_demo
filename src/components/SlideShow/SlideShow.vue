<template>
  <div id="slide_show" class="carousel slide" data-ride="carousel">
    <div class="carousel-inner">
      <div class="carousel-item"
        v-for="(slide, index) in slides"
        :class="{'active':index === 0}"
        :key="slide"
      >
        <img class="d-block w-100" :src="slide">
      </div>
    </div>
    <a class="carousel-control-prev" href="#slide_show" role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#slide_show" role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
    <div></div>
  </div>
</template>

<script>
export default {
    name: 'SlideShow',
    data: function() {
      return({
        slides:[
          require("../../assets/sample/slider-1.png"),
          require("../../assets/sample/slider-2.png"),
          require("../../assets/sample/slider-3.png")
        ]
      })
    }
}
</script>

<style lang="scss">
@import '../../variable.scss';
  #slide_show {
    width: calc(100% + 30px);
    margin-left: -15px;
    @media screen and (min-width: $breakpoint-tablet){
      margin-top: -120px;
    }
    img {
      width: 100%;
      min-height: $slideshow-minheight;
      max-height: $slideshow-maxheight;
    }
  }
</style>