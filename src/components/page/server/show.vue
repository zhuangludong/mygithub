<template>
  <div class="main_contain">
    <!-- 消息通知 -->
    <van-notice-bar left-icon="volume-o">
      {{ text }}
    </van-notice-bar>
    <!-- 业务窗口 -->
    <!-- <div class="service_list">
      <div v-for="(item, index) in serverlist" :key="index" class="listbox">
        <router-link :to="item.link">
          <div class="box">
            <img :src="item.imgurl" class="imglist" />
            <div class="span">{{ item.name }}</div>
          </div>
        </router-link>
      </div>
    </div> -->

    <van-grid :column-num="2">
      <van-grid-item
        v-for="(item, index) in serverlist"
        :key="index"
        :to="item.link"
      >
        <img :src="item.imgurl" class="imglist" />
        <div class="span">{{ item.name }}</div>
      </van-grid-item>
    </van-grid>

    <!-- 轮播图 -->
    <van-swipe
      class="my-swipe"
      :autoplay="3000"
      indicator-color="white"
      :height="120"
    >
      <van-swipe-item>1</van-swipe-item>
      <van-swipe-item>2</van-swipe-item>
      <van-swipe-item>3</van-swipe-item>
      <van-swipe-item>4</van-swipe-item>
    </van-swipe>
    <van-divider content-position="left">最新资讯</van-divider>

    <div class="news_box">
      <img class="news_img" src="../../../assets/img/onlinepay.png" />
      <div>
        <h3 class="news_title">重大消息</h3>
        <p class="news_cont">
          上面代码的意思就是，通过MultipartFile读取文件信息，如果文件为空跳转到结果页并给出提示；如果不为空读取文件流并写入到指定目录，最后将结果展示到页面。
        </p>
      </div>
    </div>
    <div class="news_box">
      <img class="news_img" src="../../../assets/img/onlinepay.png" />
      <div>
        <h3 class="news_title">重大消息</h3>
        <p class="news_cont">
          上面代码的意思就是，通过MultipartFile读取文件信息，如果文件为空跳转到结果页并给出提示；如果不为空读取文件流并写入到指定目录，最后将结果展示到页面。
        </p>
      </div>
    </div>
    <van-tabbar v-model="active" route>
      <van-tabbar-item icon="home-o" replace to="/home/show"
        >主页</van-tabbar-item
      >
      <van-tabbar-item icon="friends-o" replace to="/user"
        >用户</van-tabbar-item
      >
    </van-tabbar>
  </div>
</template>

<script>
export default {
  data () {
    return {
      text: '疫情期间,努力做毕设~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~',
      serverlist: [
        { name: '在线缴费', imgurl: require('../../../assets/img/onlinepay.png'), link: '/payhome' },
        { name: '闲置交易', imgurl: require('../../../assets/img/ershoujiaoyi.png'), link: '/sell' },
        { name: '成绩查询', imgurl: require('../../../assets/img/search.png'), link: '/check' },
        { name: '考试报名', imgurl: require('../../../assets/img/sign.png'), link: '/sign' }
      ],
      loading: true,
      newimg: require('../../../assets/img/onlinepay.png')
    }
  },
  mounted () {
    this.loading = false
  }
}
</script>

<style scoped>
.main_contain {
  position: relative;
  top: 50px;
  z-index: 0;
}
.news_cont {
  margin: 13px 0 0;
  font-size: 14px;
  line-height: 20px;
}
.news_title {
  display: block;
  margin: 0;
  font-size: 18px;
  line-height: 20px;
}
.news_img {
  flex-shrink: 0;
  width: 40px;
  height: 40px;
  margin-right: 16px;
}
.news_box {
  display: flex;
  padding: 0 16px;
}
.service_list {
  position: relative;
  width: 90%;
  height: 30%;
  margin: 10px 0 34px 0;
  border: 1px solid #ebebeb;
  left: 5%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  border-radius: 10px;
}
.listbox {
  height: 45%;
  width: 23%;
  margin-top: 2%;
  text-align: center;
  line-height: 45%;
  font-size: 10px;
}
.imglist {
  width: 40%;
}
.box {
  height: 100%;
  top: 20%;
  position: relative;
}
.span {
  height: 12px;
  line-height: 12px;
  font-weight: 600;
  position: relative;
  top: 2px;
}
.my-swipe .van-swipe-item {
  color: #fff;
  font-size: 20px;
  line-height: 150px;
  text-align: center;
  background-color: #39a9ed;
}
</style>
