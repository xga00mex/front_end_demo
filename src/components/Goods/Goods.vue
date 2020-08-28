<template>
  <div class="goods row">
    <div class="col-12 stock_title">
      <p>{{title}}</p>
      <div class="page_btns">
        <button v-on:click="goodsNowPageMinus()">
          <font-awesome-icon :icon="['fas', 'chevron-left']" size="2x"/>
        </button>
        <button v-on:click="goodsNowPageAdd()">
          <font-awesome-icon :icon="['fas', 'chevron-right']" size="2x"/>
        </button>
      </div>
    </div>
    <div class="col-12 col-md-3 stock_page"
      v-for="item in nowGoodsShow"
      :key="item.item_name"
    >
      <GoodsItem :item="item" goodsPageShow="goodsPageShow"/>
    </div>
  </div>
</template>

<script>
import GoodsItem from './GoodsItem.vue'
export default {
  name: 'Goods',
  components:{
    GoodsItem
  },
  props: ['title', 'goods_name'],
  mounted: function(){
    this.goodsList = require(`../../assets/sample/${this.goodsNames}.json`)
    window.addEventListener('resize', this.goodsPageShowChange)
    this.goodsPageShowChange()
  },
  data: function(){
    return({
      goodsNames: this.goods_name,
      goodsNowPage: 1,
      goodsPageShow: 4,
      goodsList: [
        {
          "item_name": "",
          "sale": false,
          "discount": 0,
          "vintage": "",
          "country": "",
          "region": "",
          "size": "",
          "onstock": 0,
          "price": "",
          "score": {
            "AM":"",
            "WS":"",
            "WA":""
          },
          "favorite":false,
          "image_src":""
        }
      ]
    })
  },
  methods:{
    goodsPageShowChange() {
      if (window.innerWidth < 768) {
        this.goodsPageShow = 1
      }else{
        this.goodsPageShow = 4
      }
    },
    goodsNowPageAdd() {
      if(this.goodsNowPage === this.goodsPages){
        this.goodsNowPage = 1
      }else{
        this.goodsNowPage += 1
      }
    },
    goodsNowPageMinus() {
      if(this.goodsNowPage === 1){
        this.goodsNowPage = this.goodsPages
      }else{
        this.goodsNowPage -= 1
      }
    }
  },
  computed:{
    nowGoodsShow: function(){
      return this.goodsList.slice((this.goodsNowPage-1)*this.goodsPageShow, this.goodsNowPage*this.goodsPageShow)
    },
    goodsPages: function(){
      return Math.ceil(this.goodsList.length / this.goodsPageShow)
    }
  },

}
</script>

<style lang="scss">
@import '../../variable.scss';
  .goods {
    margin-top: 3%;
    font-size: 12px;
    .stock_title {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-top: 20px;
      p {
        display: inline-block;
        font-size: 4em;
        margin-bottom: 0px;
        @media screen and (max-width: $breakpoint-tablet - 1px){
          font-size: 2em;
        }
      }
      .page_btns {
        display: inline-block;
        button {
          margin: 1px;
          outline: none;
          background-color: white;
          border: 1px #745949 solid;
        }
      }
      padding: 0px 50px;
      @media screen and (max-width: $breakpoint-tablet - 1px){
        padding: 0px 20px;
      }
    }
    .stock_page {
      margin-top: 20px;
    }
  }
</style>