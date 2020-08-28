<template>
  <div class="goods_item" >
    <div class="onsale" v-if="itemData.sale">sale</div>
    <div class="goods_detail row">
      <div class="goods_info col-8">
        <p class="item_name">{{itemData.item_name}}</p>
        <div class="score_box row">
          <div class="item_score col-4">
            <p class="score_title">AM</p>
            <p class="score_num">{{itemData.score.AM}}</p>
          </div>
          <div class="item_score col-4">
            <p class="score_title">WS</p>
            <p class="score_num">{{itemData.score.WS}}</p>
          </div>
          <div class="item_score col-4">
            <p class="score_title">WA</p>
            <p class="score_num">{{itemData.score.WA}}</p>
          </div>
        </div>
        <div class="out_of_stack">
          <p v-if="item.onstock === 0">OUT OF STACK</p>
        </div>
        <div class="item_details">
          <div class="row">
            <div class="item_detail_title">Vintage:</div>
            <div class="item_detail_text">{{itemData.vintage}}</div>
            <div class="col-5"></div>
          </div>
          <div class="row">
            <div class="item_detail_title">Country:</div>
            <div class="item_detail_text">{{itemData.country}}</div>
            <div class="col-5"></div>
          </div>
          <div class="row">
            <div class="item_detail_title">Region:</div>
            <div class="item_detail_text">{{itemData.region}}</div>
            <div class="col-5"></div>
          </div>
          <div class="row">
            <div class="item_detail_title">Size:</div>
            <div class="item_detail_text">{{itemData.size}}</div>
            <div class="col-5"></div>
          </div>
        </div>
        <div class="item_price">
          <p v-if="!itemData.sale">{{itemData.price}}</p>
          <p v-if="itemData.sale" class="discount_price">{{itemData.discount}}</p>
          <p v-if="itemData.sale"><s>{{itemData.price}}</s></p>
        </div>
      </div>
      <div class="goods_image col-4">
        <img :src="imageSrc" alt="">
      </div>
    </div>
    <div class="goods_cart">
      <div class="cart_btns">
        <button class="cart_btn" @click="addToCartMinus">-</button>
        <input class="cart_input" v-model="addToCart" type="number" :max="itemData.onstock">
        <button class="cart_btn" @click="addToCartAdd">+</button>
      </div>
      <div>
        <button class="add_to_cart" :disabled="itemData.onstock == 0">Add to cart</button>
      </div>
      <div></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GoodsItem',
  props:['item','goodsPageShow'],
  data: function(){
    return ({
      itemData: this.item,
      addToCart:0
    })
  },
  methods:{
    addToCartAdd() {
      if(this.addToCart < this.itemData.onstock){
        this.addToCart += 1
      }
      console.log(this.addToCart)
    },
    addToCartMinus() {
      if(this.addToCart > 0){
        this.addToCart -= 1
      }
      console.log(this.addToCart)
    }
  },
  computed:{
    imageSrc: function(){
      return require(`../../assets/sample/${this.item.image_src}`)
    }
  }
}
</script>

<style lang="scss">
@import '../../variable.scss';
  .goods_item {
    box-shadow: 0px 0px 5px gray;
    .onsale {
      text-align: center;
      background-color: red;
      color: white;
      width:80px;
      height:30px;
      position: absolute;
      top: -20px;
      left: 5px;
      font-size: 20px;
    }
    .goods_detail {
      @media screen and (min-width: $breakpoint-tablet){
        &:hover {
          .goods_info{
            .item_details {
              display: block;
              position: absolute;
              top:0px;
              width: 150%;
              margin:-15px;
              height: calc(100% + 30px);
              background-color: #4e1e1edc;
              color:white;
              z-index:500;
              font-size: 1.2em;
              padding: 15px;
            }
          }
        }
      }
      padding: 15px;
      .goods_info {
        .item_name {
          text-overflow: ellipsis;
          height: 150px;
          font-size: 1.5em;
          line-height: 1em;
          @media screen and (max-width: $breakpoint-tablet - 1px){
            height: 90px;
          }
        }
        .score_box {
          .item_score {
            display: flex;
            text-align: center;
            flex-direction: column;
            padding-left: 10px;
            padding: 0px 5px;
            p {
              margin-bottom: 0px;
              border: 1px black solid;
              margin-top: -1px;
            }
            .score_title {
              background-color: #664b4b;
              color: white;
            }
            .score_num {
              min-height: 40px;
              display: flex;
              align-items: center;
              justify-content: center;
            }
          }
        }
        .out_of_stack {
          min-height: 20px;
          text-align: center;
          font-weight: 700;
          color: red;
          p {
            margin-bottom: 0px;
          }
        }
        .item_details {
          .item_detail_title {
            min-width:100px;
            padding-left: 10px;
          }
          @media screen and (min-width: $breakpoint-tablet){
            display: none;
          }
        }
        .item_price {
          margin: 15px -15px 0px -10px;
          font-size: 1.5em;
          color: #4e1e1e;
          .discount_price {
            color: red;
            font-size: 1.1em;
            margin-bottom: 0px;
          }
        }
      }
      .goods_image {
        height:350px;
        padding-left: 0px;
        img {
          padding-top: 30px;
          max-width:100%;
          max-height:350px;
        }
      }
    }
    .goods_cart {
      background-color: #ad897a;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: space-around;
      .cart_btns {
        text-align: center;
        max-width: 120px;
        .cart_btn {
          border: 1px white solid;
          background-color: #ad897a;
          color: white;
          outline: none;
          min-width: 20px;
        }
        .cart_input {
          width: 30%;
        }
        .cart_input::-webkit-outer-spin-button,
        .cart_input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
        }
      }
      .add_to_cart {
        outline: none;
        border: none;
        border-radius: 15px;
        padding-right: 5px;
        min-width: 80px;
        color: white;
        background-color: #4e1e1e;
      }
    }
  }
</style>