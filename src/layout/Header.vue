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
            <router-link class="nav-brand" to="/" tag="a">
                <img src="../assets/img/logo.png" alt="">
            </router-link>
            <div class="navbar">
                <ul class="nav">
                    <li class="nav-item">
                        <a class="nav-link">
                          <span class="title">Pages</span>
                        </a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link">
                          <span class="title">Instructors</span>
                        </a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link">
                          <span class="title">Blog</span>
                        </a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link">
                          <span class="title">Courses</span>
                        </a>
                    </li>
                    <li class="nav-item is-active">
                        <a class="nav-link">
                          <span class="title">Demos</span>
                          <i class="el-icon-arrow-down icon"></i>
                          <div class="drop-menu">
                            <a href="#" class="menu-item">Demo1</a>
                            <a href="#" class="menu-item">Demo2</a>
                          </div>
                        </a>
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
@import '~assets/scss/variable';

.header {
  background-color: $color-bg-header;
  font-size: 14px;
  font-weight: 400;
  .header-top {
    height: 55px;
    line-height: 55px;
    .container {
      a {
        color: $color-text-header;
        &:hover {
          color: $color-normal;
        }
      }
      i {
        font-size: 14px;
        font-weight: 900;
        margin-right: 5px;
        color: $color-text-header;
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
  .header-bottom {
    background-color: $color-normal;
    .container {
      display: flex;
      align-items: center;
      height: 110px;
      .nav-brand {
        display: inline-block;
        width: 190px;
        img {
          display: block;
          width: 100%;
        }
      }
      .navbar {
        flex: 1 0 0;
        height: 100%;
        .nav {
          height: 100%;
          .nav-item {
            float: right;
            height: 100%;
            &.is-active {
              .nav-link {
                color: $color-blue;
                &::after {
                  position: absolute;
                  bottom: 0px;
                  left: 0;
                  right: 0;
                  height: 4px;
                  content: '';
                  background-color: $color-blue;
                }
              }
            }
            .nav-link {
              position: relative;
              cursor: pointer;
              padding-left: 2em;
              padding-right: 2em;
              line-height: 110px;
              display: block;
              font-size: 16px;
              color: $color-text-nav-unselected;
              font-weight: 700;
              .icon {
                position: absolute;
                right: 14px;
                top: 0;
                font-size: 12px;
                line-height: 110px;
                font-weight: 700;
                transition: transform 0.4s cubic-bezier(0.5, 0, 0.5, 1);
              }
              .drop-menu {
                position: absolute;
                left: 0;
                top: 100%;
                z-index: 11;
                transition: opacity 0.3s ease;
                height: 0;
                opacity: 0;
                background-color: $color-normal;
                .menu-item {
                  display: block;
                  color: #6d8591;
                  font-size: 1em;
                  font-weight: 600;
                  line-height: 24px;
                  padding: .5em 15px !important;
                  width: 200px;
                  &:hover {
                    background-color: $color-blue;
                    color: $color-normal;
                  }
                }
              }
              &:hover {
                color: $color-blue;
                .icon {
                  transform: rotate(180deg);
                }
                .drop-menu {
                  opacity: 1;
                  height: auto;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
