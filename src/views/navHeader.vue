<template>
  <div>
    <router-view></router-view>
    <el-row>
      <el-col :span="24" class="header">
        <el-col
          :span="10"
          class="logo"
          :class="collapsed?'logo-collapse-width':'logo-width'"
        >{{collapsed?'':sysName}}</el-col>
        <!-- 缩进按钮 -->
        <!-- <el-col :span="10">
				<div class="tools" @click.prevent="collapse">
					<i class="fa fa-align-justify"></i>
				</div>
        </el-col>-->
        <el-col :span="10">
          <el-menu
            :default-active="$route.path"
            router
            mode="horizontal"
            background-color="#545c64"
            text-color="#fff"
            active-text-color="#ffd04b"
          >
            <template v-for="(item,index) in $router.options.routes" v-if="!item.hidden">
              <el-submenu :index="index+''" v-if="!item.leaf">
                <template slot="title">
                  <i :class="item.iconCls"></i>
                  {{item.name}}
                </template>
                <el-menu-item
                  v-for="child in item.children"
                  :index="child.path"
                  :key="child.path"
                  v-if="!child.hidden"
                >{{child.name}}</el-menu-item>
              </el-submenu>
              <el-menu-item v-if="item.leaf&&item.children.length>0" :index="item.children[0].path">
                <i :class="item.iconCls"></i>
                {{item.children[0].name}}
              </el-menu-item>
            </template>
          </el-menu>
        </el-col>

        <el-col :span="4" class="userinfo">
          <el-dropdown trigger="click">
            <span class="el-dropdown-link userinfo-inner">
              <img :src="this.sysUserAvatar">
              {{sysUserName}}
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>我的消息</el-dropdown-item>
              <el-dropdown-item>设置</el-dropdown-item>
              <el-dropdown-item divided @click.native="logout">退出登录</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-col>
      </el-col>
    </el-row>
  </div>
</template>
<script>
export default {
  data() {
    return {
      sysName: "重构测试",
      collapsed: false,
      sysUserName: "",
      sysUserAvatar: ""
    };
  },
  methods: {
    //退出登录
    logout: function() {
      var _this = this;
      this.$confirm("确认退出吗?", "提示", {
        //type: 'warning'
      })
        .then(() => {
          sessionStorage.removeItem("user");
          _this.$router.push("/login");
        })
        .catch(() => {});
    }
  },
  mounted() {
    console.log(this.$router);
    console.log("----------------------");
    var user = sessionStorage.getItem("user");
    if (user) {
      user = JSON.parse(user);
      this.sysUserName = user.name || "";
      this.sysUserAvatar = user.avatar || "";
    }
  }
};
</script>

<style scoped lang="scss">
@import "~scss_vars";

.header {
  height: 60px;
  line-height: 60px;
  background: $color-primary;
  color: #fff;
  .userinfo {
    text-align: right;
    padding-right: 35px;
    float: right;
    .userinfo-inner {
      cursor: pointer;
      color: #fff;
      img {
        width: 40px;
        height: 40px;
        border-radius: 20px;
        margin: 10px 0px 10px 10px;
        float: right;
      }
    }
  }
  .content-wrapper {
    background-color: #fff;
    box-sizing: border-box;
  }
  .logo {
    //width:230px;
    height: 60px;
    font-size: 22px;
    padding-left: 20px;
    padding-right: 20px;
    border-color: rgba(238, 241, 146, 0.3);
    border-right-width: 1px;
    border-right-style: solid;
    img {
      width: 40px;
      float: left;
      margin: 10px 10px 10px 18px;
    }
    .txt {
      color: #fff;
    }
  }
  .logo-width {
    width: 230px;
  }
  .logo-collapse-width {
    width: 60px;
  }
  .tools {
    padding: 0px 23px;
    width: 14px;
    height: 60px;
    line-height: 60px;
    cursor: pointer;
  }
}
</style>
