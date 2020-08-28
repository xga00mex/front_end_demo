<template>
  <div id="app" class="container-fluid">
    <HeaderNavBar/>
    <SlideShow/>
    <MainService/>
    <Goods 
      title="Ponti's top picks" 
      goods_name="top-pick"
    />
    <Goods 
      title="New arrival..." 
      goods_name="new-arrival"
    />
    <Footer/>
  </div>
</template>

<script>
import HeaderNavBar from './components/headerNavber/HeaderNavBar.vue'
import SlideShow from './components/SlideShow/SlideShow.vue'
import MainService from './components/MainService/MainService.vue'
import Footer from './components/Footer/Footer.vue'
import Goods from './components/Goods/Goods.vue'

export default {
  name: 'App',
  components: {
    HeaderNavBar,
    SlideShow,
    MainService,
    Goods,
    Footer
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width:100%;
}
</style>
