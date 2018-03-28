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
          placeholder="请输入内容">
          <i slot="suffix" class="el-input__icon el-icon-search"></i>
          </el-input>
          </div>
          <el-button type="text">登录</el-button>
          <el-button type="success">开通会员</el-button>
          <el-button>开通付费包</el-button>  
        </div>
      </div>
      <div class="top_router">
        <ul>
          <li class="router_ul"><a href="">首页</a></li>
          <li class="router_ul"><a href="">歌手</a></li>
          <li class="router_ul"><a href="">专辑</a></li>
          <li class="router_ul"><a href="">排行</a></li>
          <li class="router_ul"><a href="">MV</a></li>
        </ul>
      </div>
    </div>
  </el-header>
  <el-main>
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
  min-width: 1050px;;
  padding:0 50px;
  .top_nav{
    height:90px;

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
    min-width: 500px;
  }
  }
  .top_router{
    height: 50px;
    line-height: 50px;
    border-top: 1px solid #f2f2f2;
    ul{
      list-style: none;
      li{
        display:inline-block;
        margin:0 40px;
        a{
          text-decoration: none;
        }
      }
    }
  }
}
@media screen and (max-width:1150px){
    .mod_head .top_nav_after .search_input{
      width: 40px;
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

