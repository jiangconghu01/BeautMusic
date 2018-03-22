<template>
  <div id="app">

<el-container>
  <el-header height="140px">
      <div class="mod_head">
      <div class="top_nav">
        <ul class="top_nav_ul">
          <li class="nav_ul_itm"><a href="#">LOGO</a></li>
          <li class="nav_ul_itm"><a href="#">音乐馆</a></li>
          <li class="nav_ul_itm"><a href="#">我的音乐</a></li>
          <li class="nav_ul_itm"><a href="#">客户端</a></li>
          <li class="nav_ul_itm"><a href="#">音乐号</a></li>
        </ul>
        <div class="top_nav_after">
          <div class="search_input">
          <el-input
          placeholder="请输入内容"
          v-model="input23">
          <i slot="suffix" class="el-input__icon el-icon-search"></i>
          </el-input>
          </div>
          <el-button type="text">登录</el-button>
          <el-button type="success">开通会员</el-button>
          <el-button>开通付费包</el-button>  
        </div>
      </div>
    </div>
  </el-header>
  <el-main>
    <el-button type="success">文本的按钮</el-button>
    <router-view/>
  </el-main>
  <el-footer height="250px">Footer</el-footer>
</el-container>

  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="scss">
@import 'css/base';
.mod_head{
  width: 100%;
  ul{
     list-style: none;
     display: inline;
    li{
      display: inline-block;
      width: 100px;
      line-height: 100px;
      height: 100px;
      a{
        text-decoration: none;
      }
    }
  }
  .top_nav_after{
    .search_input{
      display: inline-block;
    }
    display: inline-block;
    width: 600px;
  }
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.el-header, .el-footer {
    background-color: rgba(162, 235, 121, 0.5);
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
</style>

