<template lang='pug'>
  section.gray
    .detail-header
      .cover-msg
        image.cover(mode="aspectFill",:src="basketballInfo.cover")
        .msg
          h5.name {{basketballInfo.placeName}}
          p [{{basketballInfo.area}}]
          p 收费模式：{{basketballInfo.price}}
          p 提供者：{{basketballInfo.devoter}}
      .detail-itro
        i.iconfont.icon-shijian.small-icon
        span 全天开放，夜间有灯光
      .detail-itro.place-tel
        div.location
          i.iconfont.icon-dingwei.small-icon
          span 浙江大学紫金港校区内部
        .tel
          i.iconfont.icon-web-icon-
    .other-detail.white-column
      h5.small-title 其他描述
      p 塑胶场地，很平整，适合打比赛
    .other-detail.white-column
      h5.small-title 照片墙
      image.w100(mode="aspectFill",v-for="(item,index) in basketballInfo.imgList", :src="item", :data-src="item", :key="index",@click="previewImage(index)")
</template>

<script>
import ex from '@/assets/images/exPlace.jpg';
export default {
  data () {
    return {
      basketballInfo: {
        id: 1,
        cover: ex,
        placeName: '浙江大学篮球场',
        price: '10元/次',
        devoter: '郑飞',
        area: '西湖区',
        imgList: ['http://fa.topitme.com/a/b5/71/112111949416071b5ao.jpg', 'http://images4.c-ctrip.com/target/fd/cruise/g2/M01/6B/71/CghzgVWNB32ATlloADJ2ieIRJHw666.jpg', 'http://file.youboy.com/a/28/86/67/7/18833927.jpg', 'http://dimg01.c-ctrip.com/images/fd/tg/g5/M03/F2/62/CggYsFbJ8haAUhXVAAKVXsytarU204.jpg']
      }
    }
  },
  onLoad () {
    console.log(this.$root.$mp.query);
  },
  methods: {
    previewImage (index) {
      let imgObj = {};
      imgObj.current = this.basketballInfo.imgList[index];
      imgObj.urls = this.basketballInfo.imgList;
      wx.previewImage(imgObj);
    }
  }
}
</script>

<style lang='scss' scoped>
  .detail-header{
    background:#fff;
    margin-bottom:40rpx;
    .cover-msg{
      border-bottom:2rpx solid #eee;
      padding: 20rpx;
      display:flex;
      font-size:24rpx;
      color:#666;
      .cover{
        height:180rpx;
        margin-right:30rpx;
        flex:1;
      }
      .msg{
        flex:2;
        .name{
          font-size:28rpx;
          color:#000;
          margin-bottom:10rpx;
        }
        p{
          margin-bottom:15rpx;
        }
      }
    }
  }
  .detail-itro{
    padding:20rpx;
    border-bottom:2rpx solid #eee;
    font-size:24rpx;
    color:#666;
    position: relative;
    display:flex;
    align-items: center;
    &.place-tel{
      justify-content:space-between;
    }
    .small-icon{
      font-size:26rpx;
      color:#888;
      margin-right:20rpx;
      vertical-align: middle;
    }
    .tel{
      .iconfont{
        font-size:40rpx;
        border-left:2rpx solid #e8e8e8;
        padding-left:10rpx;
        color:#000;
      }
    }
  }
  .other-detail{
    font-size:24rpx;
    color:#666;
    line-height:1.8;
    margin-bottom:40rpx;
    .w100{
      width:100%;
      margin-bottom:20rpx;
    }
  }
</style>

