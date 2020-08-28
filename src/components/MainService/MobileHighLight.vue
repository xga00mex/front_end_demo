<template>
  <div class="row highlight_box">
    <div class="col-12 d-md-none highlight_item">
      <img src="../../assets/sample/heightlight-mobile-1.png" alt="">
      <div class="highlight_text">
        <h6>標題1</h6>
        <p>圖太糊字看不清楚</p>
      </div>
    </div>
    <div class="col-12 d-md-none highlight_item">
      <img src="../../assets/sample/heightlight-mobile-2.png" alt="">
      <div class="highlight_text">
        <h6>標題2</h6>
        <p>圖太糊字看不清楚</p>
      </div>
    </div>
    <div class="col-12 d-md-none highlight_item">
      <img src="../../assets/sample/heightlight-mobile-3.png" alt="">
      <div class="highlight_text">
        <h6>標題3</h6>
        <p>圖太糊字看不清楚</p>
      </div>
    </div>
    <div class="col-12 d-md-none highlight_item">
      <img src="../../assets/sample/heightlight-mobile-4.png" alt="">
      <div class="highlight_text">
        <h6>標題4</h6>
        <p>圖太糊字看不清楚</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:"HighLight"
}
</script>

<style lang="scss">
@import '../../variable.scss';
  .highlight_box {
    .highlight_item{
      margin-bottom: 15px;
      .highlight_text {
        position: absolute;
        bottom: 0px;
        width: calc( 100% - 30px);
        text-align: center;
        color: white;
        background-color: #3d1c1ca8;
        h6, p {
          margin: 0px auto;
        }
      }
    }
    img {
      width: 100%;
    }
    padding: 0px 60px;
    @media screen and (max-width: $breakpoint-tablet - 1px){
      padding: 0px 20px;
    }
  }
</style>