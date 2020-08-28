<template>
  <div class="row highlight_box">
    <div class="col-md-3 d-none d-md-block">
      <img src="../../assets/sample/heightlight-desktop-1.png" alt="">
      <div class="highlight_text">
        <h6>標題1</h6>
        <p>圖太糊字看不清楚</p>
      </div>
    </div>
    <div class="col-md-3 d-none d-md-block">
      <img src="../../assets/sample/heightlight-desktop-2.png" alt="">
      <div class="highlight_text">
        <h6>標題2</h6>
        <p>圖太糊字看不清楚</p>
      </div>
    </div>
    <div class="col-md-3 d-none d-md-block">
      <img src="../../assets/sample/heightlight-desktop-3.png" alt="">
      <div class="highlight_text">
        <h6>標題3</h6>
        <p>圖太糊字看不清楚</p>
      </div>
    </div>
    <div class="col-md-3 d-none d-md-block">
      <img src="../../assets/sample/heightlight-desktop-4.png" alt="">
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
  .highlight_box {
    padding: 0px 60px;
    img {
      width: 100%;
    }
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
</style>