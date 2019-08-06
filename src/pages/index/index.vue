<template>
  <div>
    <swiper
      v-if="imgUrls.length > 0"
      indicator-dots="true"
      autoplay="true"
      interval="2000"
      style="height: 240px;"
    >
      <block v-for="(item, index) in imgUrls" :key="index">
        <swiper-item>
          <image :src="item" style="width:100%;height:240px;" />
        </swiper-item>
      </block>
    </swiper>

    <div class="icons_area">
      <div class="icons_looper" v-for="(item,index) in iconslist" :key="index">
        <div style="text-align: center">
          <img :src="item.imgsrc" class="looper_img">
        </div>
        <div class="looper_title">{{item.title}}</div>
        </div>
    </div>

    <div class="title_header">
      <div class="title_header_left"></div>
      <div class="title_header_title">店长推荐</div>
      <div class="title_header_right"></div>
    </div>
    <div class="inline">
      <div v-for="(item, index) in list" :key="index" class="inline_1">
        <navigator :url="item.link">
          <img :src="item.src" style="width:100%;height:80px;" />
          <div class="inline_title">{{item.title}}</div>
        </navigator>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      motto: "Hello miniprograme",
      imgUrls: [
        require("../../../static/images/banner/banner002.png"),
        require("../../../static/images/banner/banner003.png"),
        require("../../../static/images/banner/banner004.png"),
        require("../../../static/images/banner/banner005.png"),
        require("../../../static/images/banner/banner006.png")
      ],
      list: [
        {
          src: require("../../../static/images/dashboard/0001.png"),
          title: "碧螺春",
          link: "../tea01/main"
        },
        {
          src: require("../../../static/images/dashboard/0002.png"),
          title: "扁茶",
          link: "../tea02/main"
        },
        {
          src: require("../../../static/images/dashboard/0003.png"),
          title: "滚筒-粗",
          link: "../tea03/main"
        },
        {
          src: require("../../../static/images/dashboard/0004.png"),
          title: "滚筒-细",
          link: "../tea04/main"
        },
        {
          src: require("../../../static/images/dashboard/0005.png"),
          title: "红茶-粗",
          link: "../tea05/main"
        },
        {
          src: require("../../../static/images/dashboard/0006.png"),
          title: "红茶-细",
          link: "../tea06/main"
        }
      ],
      iconslist: [
        {
          imgsrc: require("../../../static/images/icons/icon00.png"),
          title: "弘韵留茗"
        },
        {
          imgsrc: require("../../../static/images/icons/icon01.png"),
          title: "赠友佳品"
        },
        {
          imgsrc: require("../../../static/images/icons/icon02.png"),
          title: "天然绿色"
        },
        {
          imgsrc: require("../../../static/images/icons/icon03.png"),
          title: "留香难忘"
        }
      ],
      userInfo: {
        nickName: "mpvue",
        avatarUrl: "http://mpvue.com/assets/logo.png"
      }
    };
  }
};
</script>
<style lang="scss" scoped>
.icons_area {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 90%;
  margin: 20px auto 20px auto;
  .icons_looper {
    flex: 1;
    .looper_img {
      width: 40px;
      height: 40px;
    }
    .looper_title {
      text-align: center;
      font-size: 14px;
      color: #000;
      font-weight: 700;
    }
  }
}
.title_header {
  font-size: 0;
  height: 15px;
  width: 300px;
  margin: 20px auto 20px auto;
  .title_header_left {
    background-image: url("../../../static/images/title_left.png");
    background-size: 100% 100%;
    height: 30px;
    width: 110px;
    display: inline-block;
    vertical-align: top;
  }
  .title_header_title {
    font-size: 18px;
    width: 80px;
    color: #000;
    display: inline-block;
    vertical-align: top;
    text-align: center;
    font-weight: 700;
  }
  .title_header_right {
    background-image: url("../../../static/images/title_right.png");
    background-size: 100% 100%;
    height: 30px;
    width: 110px;
    display: inline-block;
    vertical-align: top;
  }
}
.inline {
  display: inline-block;
  width: 100%;
  margin-top: 20px;
  padding: 0 5%;
  font-size: 0;
  .inline_1 {
    width: 28%;
    padding: 0 1%;
    display: inline-block;
  }
  .inline_title {
    font-size: 14px;
    line-height: 18px;
    font-weight: normal;
    color: #333;
    text-align: center;
  }
}
</style>

<style scoped>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all {
  width: 7.5rem;
  height: 1rem;
  background-color: blue;
}
.all:after {
  display: block;
  content: "";
  clear: both;
}
.left {
  float: left;
  width: 3rem;
  height: 1rem;
  background-color: red;
}

.right {
  float: left;
  width: 4.5rem;
  height: 1rem;
  background-color: green;
}
</style>
