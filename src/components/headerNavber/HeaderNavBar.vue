<template>
  <div class="header_box">
    <header 
      class="main_header row"
      :class="{
        'topHeader':isTop,
        'notTopHeader':!isTop
      }"
    >
      <div 
        class="col-md-4 header_top header_contact flex_center d-none d-md-block" 
        v-if="isTop & !isMobile"
      >
        <div>
          <b>TEL </b>(852)2739 7678
          <br>
          <b>EMAIL </b>enquiries@pontiwinecellars.com
        </div>
      </div>
      <div 
        class="header_top header_logo flex_center order-1" 
        :class="{
          'col-md-4':isTop & !isMobile,
          'col-md-2':!isTop & !isMobile,
          'col-8 order-2': isMobile
        }"
      >
        <img :src="logoSrc" alt="img not found">
      </div>
      <div 
        class="header_top header_user" 
        :class="{
          'col-md-4 order-2':isTop & !isMobile,
          'col-md-3 order-3':!isTop & !isMobile,
          'col-2 order-3': isMobile
        }"
      >
        <a class="header_login_btn d-none d-md-block">Log in</a>
        <a class="header_register_btn d-none d-md-block">Register</a>
        <a href="#"
          v-if="!isMobile"
        >
          <font-awesome-icon icon="search" size="2x" />
        </a>
        <a href="#">
          <font-awesome-icon icon="shopping-cart" size="2x" />
        </a>
      </div>
      <div 
        class="header_nav flex_center" 
        :class="{
          'col-md-12 order-3': isTop & !isMobile,
          'col-md-7 order-2': !isTop & !isMobile,
          'd-none': isMobile
        }"
      >
        <desktopNav v-if="!isMobile"/>
      </div>
      <mobileNavButton 
        v-if="isMobile"
        :class="{
          'col-2 order-1': isMobile
        }"
      />
    </header>
    <mobileNavCollapse v-if="isMobile"/>
  </div>
</template>

<script>
const DesktopNav = () => import('./DesktopNav.vue')
const MobileNavButton = () => import('./MobileNavButton.vue')
const MobileNavCollapse = () => import('./MobileNavCollapse.vue')

export default {
  name: 'HeaderNavBar',
	components: { 
    DesktopNav, MobileNavButton, MobileNavCollapse
	},
  mounted: function(){
    window.addEventListener('scroll', this.isTopCheck)
    window.addEventListener('resize', this.isMobileCheck)
    this.isMobileCheck()
  },
  data: function(){
    return(
      {
        isTop: true,
        isMobile: false,
        logoSrc: '../assets/sample/ponti-wine-cellars-logo-1589532960.jpg.png'
      }
    )
  },
  methods: {
    isTopCheck(){
      if(document.documentElement.scrollTop === 0){
        this.isTop = true
      }else{
        this.isTop = false
      }
    },
    isMobileCheck() {
      if (window.innerWidth < 768) {
        this.isMobile = true
      }else{
        this.isMobile = false
      }
      this.logoSwitch()
    },
    logoSwitch() {
        this.logoSrc = this.isMobile ? require("../../assets/sample/ponti_wine_cellars-logo BLACK.png") : require("../../assets/sample/ponti-wine-cellars-logo-1589532960.jpg.png")
    }
  }
}
</script>

<style lang="scss">
@import '../../variable.scss';
  .header_box {
    position: sticky;
    top: 0;
    z-index: 1000;
    .main_header {
      color: $navbar-text-color;
      background-color: $navbar-background-color;
      .header_contact {
        margin-top: 1em;
      }
      .header_logo{
        img {
          max-width: 110px;
          padding:5px;
        }
      }
      .header_user {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: flex-end;
        a { 
          color: $navbar-text-color;
          padding: 0px 5px;
          @media screen and (max-width: $breakpoint-tablet - 1){
            color: $navbar-text-color-mobile
          }
        }
        .header_login_btn{
          border-right: 2px $navbar-text-color solid;
        }
      }
      .header_nav {
        a {
          color: $navbar-text-color;
        }
        a:hover, a:focus{
          font-weight: 700;
        }
      }
      @media screen and (max-width: $breakpoint-tablet - 1){
        background-color: $navbar-background-color-mobile;
      }
    }
  }
  .flex_center {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: center;
      padding: 0px;
  }
  @media screen and (max-width: $breakpoint-laptop - 1){
    a, div {
      font-size: 0.8rem;
    }
  }
</style>