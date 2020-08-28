<template>
  <div class="collapse navbar-collapse header_navbar_member" id="header_navbar">
    <div 
      class="collapse_close_btn"
      :click="hideHeaderNavbar"
    >
      <font-awesome-icon icon="times" size="2x"/>
    </div>
    <ul class="navbar-nav header_navbar_member">
      <li class="nav-item header_navbar_member"
        v-for="member in header_navbar_member_top"
        :key="member[0]"
      >
        <a class="nav-link header_navbar_member" :href="member[1]">{{member[0]}}</a>
      </li>
      <li class="nav-item header_navbar_split header_navbar_member"></li>
      <li class="nav-item header_navbar_member"
        v-for="member in header_navbar_member_bottom"
        :key="member[0]"
      >
        <a class="nav-link header_navbar_member" :href="member[1]">{{member[0]}}</a>
      </li>
    </ul>
  </div>
</template>

<script>
import $ from 'jquery'
export default {
  name: 'MobileNavCollapse',
  mounted: function() {
    let self = this
    window.addEventListener('click', function(e){
      if((!e.target.classList.contains('header_navbar_member'))){
        self.hideHeaderNavbar()
      }
    })
  },
  data: function(){
    return({
      header_navbar_member_top: [
        ['LOG IN/REGISTER', '#'],
        ['SHOP', '#'],
        ['PROMOTIONS', '#'],
        ['EVENTS', '#'],
        ['ABOUT US', '#'],
        ['CONTACT', '#']
      ],
      header_navbar_member_bottom: [
        ['PRIVACY&POLICY', '#'],
        ['TERMS OF USE', '#'],
        ['COOKIES POLICY', '#'],
        ['FAQ', '#'],
        ['SEARCH', '#'],
      ]
    })
  },
  methods: {
    hideHeaderNavbar(){
      $("#header_navbar").collapse('hide')
    }
  }
}
</script>

<style lang="scss">
@import '../../variable.scss';
  #header_navbar {
    position: absolute;
    top: 70px;
    min-width: 200px;
    padding: 10px;
    background-color: white;
    box-shadow: 0px 0px 5px $shadow-color-collapse;
    a {
      color: $navbar-text-color-mobile;
    }
    .header_navbar_split {
      height: 1px;
      background-color: $navbar-split-color-collapse;
    }
    .collapse_close_btn {
      position: absolute;
      left:175px;
    }
  }
</style>