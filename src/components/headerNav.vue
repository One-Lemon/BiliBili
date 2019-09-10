<template>
  <header class="header">
    <div class="headerFlex">
      <ul class="nav">
        <router-link tag="li" v-for="Link in Links" :key="Link.id" :to="Link.link">
          <a class="link">{{Link.name}}</a>
        </router-link>
      </ul>
      <div>
        <el-input placeholder="你凑啥，有本事搜啊" v-model="search" class="input-with-select" size="medium">
          <el-button slot="append" icon="el-icon-search" @click="onSearch"></el-button>
        </el-input>
      </div>
      <div class="iconFlex">
        <el-avatar icon="el-icon-user-solid" size="medium" style="margin-right: 20px;"></el-avatar>
        <i class="el-icon-help navIcon"></i>
        <i class="el-icon-refrigerator navIcon"></i>
        <i class="el-icon-milk-tea navIcon"></i>
        <i class="el-icon-star-off navIcon"></i>
        <i class="el-icon-toilet-paper navIcon"></i>
        <el-button type="danger">投稿</el-button>
      </div>
    </div>
    <div class="bg"></div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      Links: [
        { id: 0, name: "主站", link: "/" },
        { id: 1, name: "番剧", link: "/fan" },
        { id: 2, name: "音频", link: "/audio" },
        { id: 3, name: "游戏中心", link: "/game" },
        { id: 4, name: "直播", link: "/liveShow" },
        { id: 5, name: "会员购", link: "/vip" },
        { id: 6, name: "漫画", link: "/comic" },
        { id: 7, name: "BW", link: "/bw" },
        { id: 8, name: "70年", link: "/70years" },
        { id: 9, name: "下载App", link: "/download" }
      ],
      search: ""
    };
  },
  methods: {
    onSearch() {
      console.log(this.search);
    }
  }
};
</script>
<style lang ='less' scoped>
.nav {
  display: flex;
}
.link {
  font-size: 14px;
  color: #fff;
  text-shadow: 0 1px 1px rgba(0, 0, 0, 0.24);
  white-space: nowrap;
  margin-right: 14px;
}
.input-with-select {
  width: 460px;
  height: 32px;
}
.headerFlex {
  padding: 0 24px;
  display: flex;
  box-sizing: border-box;
  position: absolute;
  justify-content: space-between;
  z-index: 1;
  width: 100%;
  height: 56px;
  align-items: center;
}
.bg {
  margin: 0 auto;
  position: relative;
  z-index: 0;
  min-height: 155px;
  height: 9.375vw;
  min-width: 1033px;
  background-color: #f9f9f9;
  display: -ms-flexbox;
  display: flex;
  background: url(/images/navbanner.png) center no-repeat;
  -ms-flex-pack: center;
  justify-content: center;
  background-repeat: no-repeat;
  background-position: center 0;
  background-size: cover;
}
.iconFlex {
  display: flex;
  align-items: center;
}
.navIcon {
  font-size: 28px;
  margin-right: 20px;
}
</style>