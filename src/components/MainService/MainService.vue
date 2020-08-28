<template>
  <div>
    <div class="row main_service">
      <div class="col-4">
        <img src="../../assets/sample/image-53-4.png" alt="">
        <h5>Trusted Wine Delivery Service</h5>
        <p>Deliver Wines with Our New Temperature Contreolled Truck</p>
      </div>
      <div class="col-4">
        <img src="../../assets/sample/image-54-4.png" alt="">
        <h5>Incredible Value Premium Wines</h5>
        <p>Work with Producers and Negociants to Bring You Best Value Wines</p>
      </div>
      <div class="col-4">
        <img src="../../assets/sample/image-55.png" alt="">
        <h5>Free Delivery</h5>
        <p>Spend HK<b>$1,800</b> to enjoy free delivery to a single location in Hong Kong Island Kowloon or New Territoris</p>
      </div>
      <div class="col-12 service_bottom_border"></div>
    </div>
    <HighLight/>
    <MobileHighLight/>
  </div>
</template>

<script>
import HighLight from './HighLight.vue'
import MobileHighLight from './MobileHighLight.vue'
export default {
  name: "MainService",
  components:{
    HighLight,
    MobileHighLight
  }
}
</script>

<style lang="scss">
@import '../../variable.scss';
  .main_service {
    margin-top: 2em;
    text-align: center;
    img {
      width:100%;
      max-width: 130px;
    }
    h5 {
      margin-top: 10px;
    }
    p {
      @media screen and (min-width: $breakpoint-tablet){
        width: 50%;
        margin: 0 auto;
      }
    }
    .service_bottom_border {
      max-width: 50%;
      min-width: 250px;
      height: 2px;
      background-color:brown;
      margin: 2em auto;
    }
  }
</style>