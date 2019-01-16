<template>
  <div class="header">
    <div class="header-top">
      <div class="container">
        <el-row>
          <el-col :span="9" class="left">
            <div class="contacts">
              <span>
                <i class="el-icon-phone"></i>
                <a href>(+61) 38376 6284</a>
              </span>
              <span>
                <i class="el-icon-message"></i>
                <a href>support@courseware.com</a>
              </span>    
            </div>
          </el-col>
          <el-col :span="15" class="right">
            <span>
              <i class="el-icon-service"></i>
              <a href>weixin</a>
            </span>
            <span>
              <i class="el-icon-view"></i>
              <a href>weibo</a>
            </span>
            <span>
              <a href>登录</a>
            </span>
            <span>
              <a href>注册</a>
            </span>
          </el-col>
        </el-row>
      </div>
    </div>
    <div class="header-bottom">
        <div class="container">
            <router-link to="/" tag="a">
                <img src="../assets/img/logo.png" alt="">
            </router-link>
            <div class="navbar">
                <ul class="nav">
                    <li class="nav-item">
                        <a class="nav-link">Demos</a>
                    </li>
                </ul>
            </div>
        </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss">
.header {
  background-color: #2c2d36;
  color: #85858c;
  font-size: 14px;
  font-weight: 400;
  .header-top {
    height: 55px;
    line-height: 55px;
    .container {
      a {
        color: #85858c;
        &:hover {
          color: #fff;
        }
      }
      i {
        font-size: 14px;
        font-weight: 900;
        margin-right: 5px;
      }
      span {
        margin-right: 1.4em;
        &:last-child {
            margin-right: 0;
        }
      }
      .left {
          text-align: left;
      }
      .right {
          text-align: right
      }
    }
  }
  .nav {

  }
}
</style>
