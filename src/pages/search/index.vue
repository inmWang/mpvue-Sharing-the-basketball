<template lang='pug'>
  section
    .header
      input.search-input(placeholder="请输入查询的地点")
      span 搜索
    .search-list
      .no-search
        i.iconfont.icon-icon-test
        p 暂无搜索结果
        p 来分享你知道的篮球场信息吧~
        a.share-btn(href="../upload/main") 分享
</template>

<script>
export default {

}
</script>

<style lang='scss' scoped>
  .header{
    background:#181818;
    padding:10rpx 20rpx 20rpx;
    font-size:28rpx;
    display:flex;
    align-items:center;
    .search-input{
      flex-grow:1;
      background:#fff;
      border-radius:40rpx;
      padding:0 20rpx;
      margin-right:20rpx;
    }
    span{
      color:#fff;
    }
  }
  .no-search{
    display:block;
    margin:200rpx auto;
    width:80%;
    text-align:center;
    font-size:28rpx;
    color:#666;
    .iconfont{
      font-size:80rpx;
      margin-bottom:20rpx;
    }
    p{
      line-height:2;
    }
    .share-btn{
      margin:20rpx auto;
      width:250rpx;
      height:70rpx;
      text-align: center;
      display:block;
      line-height:70rpx;
      color:#fff;
      border-radius:6rpx;
      background:rgb(235, 132, 72);
    }
  }
</style>

