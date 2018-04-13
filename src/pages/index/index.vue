<template lang="pug">
  .container
    .header
      a.location
        span 杭州
        i.iconfont.icon-xiala
      a.search-group(href="../search/main")
        i.iconfont.icon-tubiao-
        span 输入地点查找附近的篮球场
    section.content
      -for(var i=0;i<10;i++)
        commonItem(:common-data="basketballInfo")
  //- <div class="container" @click="clickHandle('test click', $event)">

  //-   <div class="userinfo" @click="bindViewTap">
  //-     <img class="userinfo-avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl" background-size="cover" />
  //-     <div class="userinfo-nickname">
  //-     </div>
  //-   </div>

  //-   <div class="usermotto">
  //-     <div class="user-motto">
  //-     </div>
  //-   </div>

  //-   <form class="form-container">
  //-     <input type="text" class="form-control" v-model="motto" placeholder="v-model" />
  //-     <input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy" />
  //-   </form>
  //-   <a href="/pages/counter/main" class="counter">去往Vuex示例页面</a>
  //- </div>
</template>

<script>
import commonItem from '@/components/commonItem';
import ex1 from '@/assets/images/exPlace.jpg';
export default {
  data () {
    return {
      basketballInfo: {
        id: 1,
        cover: ex1,
        placeName: '浙江大学篮球场',
        price: '10元/次',
        devoter: '郑飞',
        area: '西湖区'
      }
      // motto: 'Hello World',
      // userInfo: {}
    }
  },
  components: {
    commonItem
  },
  methods: {
    bindViewTap () {
      // const url = '../logs/main';
      // wx.navigateTo({ url });
    },
    getUserInfo () {
      // 调用登录接口
      wx.login({
        success: () => {
          wx.getUserInfo({
            success: (res) => {
              this.userInfo = res.userInfo;
            }
          })
        }
      })
    },
    clickHandle (msg, ev) {
      console.log('clickHandle:', msg, ev);
    }
  },

  created () {
    // 调用应用实例的方法获取全局数据
    this.getUserInfo();
  }
}
</script>

<style lang="scss" scoped>
.header{
  background:#181818;
  font-size:28rpx;
  padding:10rpx 20rpx 20rpx;
  display:flex;
  .location{
    flex:1;
    // color:#dbbb92;
    color:#fff;
    position: relative;
    top:4rpx;
  }
  .search-group{
    flex:5;
    background:#fff;
    position:relative;
    padding: 0 10rpx;
    border-radius:25rpx;
    color:#565656;
    i{
      font-size:40rpx;
      vertical-align: middle;
    }
    span{
      font-size:24rpx;
      vertical-align: middle;
    }
  }
}
// .userinfo {
//   display: flex;
//   flex-direction: column;
//   align-items: center;
// }

// .userinfo-avatar {
//   width: 128rpx;
//   height: 128rpx;
//   margin: 20rpx;
//   border-radius: 50%;
// }

</style>
