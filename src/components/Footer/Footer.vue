<template>
  <footer>
    <div class="footer_nav row">
      <div class="col-12 col-md-6 about_us">
        <img src="../../assets/sample/ponti_wine_cellars-logo BLACK.png" alt="">
        <p class="about_us_text">Ponti Wine Cellars is an online wine shio in
          Hong Kong. We offer a comprehensive 
          range of top quality wines from all over the
          world such as USA,Itay,France,Spain,
          Argentina,China and etc.
        </p>
      </div>
      <div class="col-12 col-md-4 offset-md-2 footer_nav_box">
        <div class="footer_nav_items">
          <a href="#">ABOUT US</a>
          <a href="#">SHOP</a>
          <a href="#">WINE CLUB BENEFIT</a>
          <a href="#">OUR STORES</a>
          <a href="#">CONTACT US</a>
          <a href="#">FAQ</a>
          <a href="#">SITE MAP</a>
        </div>
        <div class="newsletter">
          <label for="email_address"><b>NEWSLETTER</b></label>
          <input id="email_address" type="text" placeholder="Email Address">
          <button>SUBSCRIBE</button>
          <div class="conmmunity_btns">
            <a href="#"><font-awesome-icon :icon="['fab', 'facebook-square']" size="3x"/></a>
            <a href="#"><font-awesome-icon :icon="['fab', 'instagram']" size="3x"/></a>
          </div>
        </div>
      </div>
    </div>
    <div class="footer_policy row">
      <div class="col-12 col-md-6 footer_policy_text">
        <p>Under the law of Hong Kong,intoxicating liquor must not be
          sold r supplied to a minor in the course of business.
        </p>
        <p>根據香港法律, 不得在業務過程中, 向未成年人售賣貨供應令人醺醉的酒類。</p>
        <div class="copyright d-none d-md-block">
          <span>© 2020,Ponti Wine Cellars</span>
          <span>
            <a href="#">Terms of Use</a>
            <a href="#">Privacy Policy</a>
            <a href="#">Cookies Policy</a>
          </span>
        </div>
      </div>
      <div class="col-12 col-md-4 offset-md-2 payment">
        <img src="../../assets/sample/payment.png" alt="">
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style lang="scss">
@import '../../variable.scss';
  .footer_nav {
    background-color: $footer-color;
    margin-top: 50px;
    margin-left: -15px;
    padding: 30px;
    width: calc(100% + 30px);
    .about_us {
      @media screen and (max-width: $breakpoint-tablet - 1px) {
        text-align: center;
      }
      img {
        max-width: 50%;
        max-width: 200px;
      }
      .about_us_text {
        width: 55%;
        padding: 10px;
        @media screen and (max-width: $breakpoint-tablet - 1px){
          width: 100%;
          text-align: center;
        }
      }
    }
    .footer_nav_box {
      width: 80%;
      .footer_nav_items {
        a {
          color: $footer-text-color;
          padding: 3px 0.8em;
          display: inline-block;
        }
        @media screen and (max-width: $breakpoint-tablet - 1px){
          text-align: center;
        }
      }
      .newsletter {
        margin-top: 20px;
        @media screen and (max-width: $breakpoint-tablet - 1px){
          text-align: center;
        }
        label {
          font-size: 8px;
          display: block;
          margin-bottom: 0px;
          margin-left: 10px;
          @media screen and (max-width: $breakpoint-tablet - 1px){
            margin: 0px auto;
          }
        }
        input {
          display: block;
          margin-left: 10px;
          width: 85%;
          @media screen and (max-width: $breakpoint-tablet - 1px){
            margin: 0px auto;
          }
        }
        button {
          margin-top: 5px;
          margin-left: 10px;
          padding: 5px 10px;
          font-size: 0.8em;
          border: none;
          outline: none;
          color: white;
          background-color: #b69982;
          @media screen and (max-width: $breakpoint-tablet - 1px){
            margin: 0px auto;
          }
        }
        .conmmunity_btns {
          text-align: right;
          width: 90%;
          a {
            margin-right:5px;
            color: black;
          }
          @media screen and (max-width: $breakpoint-tablet - 1px){
            text-align: center;
            margin: 15px auto 0px auto;
          }
        }
      }
    }
  }
  .footer_policy {
    margin-bottom: 20px;
    .footer_policy_text {
      font-size: 0.8em;
      margin-top: 15px;
      @media screen and (max-width: $breakpoint-tablet - 1px){
        text-align: center;
      }
      p {
        margin-bottom: 0px;
      }
      .copyright {
        margin-top: 15px;
        a {
          color: black;
          font-size: 1.5em;
          padding: 0px 15px;
        }
      }
    }
    .payment {
      padding-right: 5em;
      display: flex;
      justify-content: center;
      align-items: center;
      img {
        width: 100%;
      }
      @media screen and (max-width: $breakpoint-tablet - 1px) {
        padding-right: 15px;
      }
    }
  }
</style>