<template lang='pug'>
  a.ball-item(:href="'../detail/main?id=' + commonData.id")
    image.cover(:src="commonData.cover",mode="aspectFill")
    .ball-intro
      h5.title {{commonData.placeName}}
      p.location [{{commonData.area}}]
      p.intro
        span {{commonData.price}}
        span.author 提供者：{{commonData.devoter}}
</template>

<script>
export default {
  props: ['commonData'],
  methods: {
    // goDetail () {
    //   const url = '../detail/main';
    //   wx.navigateTo({ url });
    // }
  }
}
</script>

<style lang='scss' scoped>
.ball-item{
  display:flex;
  font-size:24rpx;
  color:#000;
  border-bottom:2rpx solid #efefef;
  padding:20rpx 0;
  &:active{
    background:rgba(0,0,0,0.1);
  }
  .cover{
    height:150rpx;
    border:2rpx solid #ccc;
    margin-right:20rpx;
    flex:1;
  }
  .ball-intro{
    flex:3;
    height:150rpx;
    position: relative;
  }
  .title{
    font-size:32rpx;
    margin-bottom:10rpx;
  }
  .intro{
    display:flex;
    position:absolute;
    bottom:0;
    width:100%;
    span{
      flex:1;
      justify-content:space-between;
      &.author{
        text-align: right;
      }
    }
  }
  .location,.intro{
    color:#666;
  }
}
</style>

