<template>
  <div class="footer">
    <div class="footer-top">
      <div class="section-padding">
        <div class="container">
          <el-row>
            <el-col :span="6">
              <div class="widget">
                <img
                  class="footer-logo"
                  src="../assets/img/logo2.png"
                  alt=""
                >
                <div class="detail">
                  <p> We are a team of different geeks that believe in producing top-quality courses and category based on best videos.</p>
                  <ul class="footer-contacts">
                    <li class="phone contact">
                      <i class="icon el-icon-phone"></i>
                      <a href="#">(+61) 38376 6284</a>
                    </li>
                    <li class="email contact">
                      <i class="icon el-icon-message"></i>
                      <a href="#">support@courseware.com</a>
                    </li>
                  </ul>
                </div>
              </div>
            </el-col>
            <el-col :span="6">
              <div class="widget">
                <h4 class="title">Quick Links</h4>
                <div class="detail">
                  <ul class="menu">
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Courses</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Events</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Concat</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Gallery</a>
                    </li>
                  </ul>
                </div>
              </div>
            </el-col>
            <el-col :span="6">
              <div class="widget">
                <h4 class="title">Quick Links</h4>
                <div class="detail">
                  <ul class="menu">
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Courses</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Events</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Concat</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Gallery</a>
                    </li>
                  </ul>
                </div>
              </div>
            </el-col>
            <el-col :span="6">
              <div class="widget">
                <h4 class="title">Quick Links</h4>
                <div class="detail">
                  <ul class="menu">
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Courses</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Events</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Concat</a>
                    </li>
                    <li class="item">
                      <a href="#"><i class="icon el-icon-d-arrow-right"></i>Gallery</a>
                    </li>
                  </ul>
                </div>
              </div>
            </el-col>
          </el-row>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="container">
        <el-row>
          <el-col :span="16">Copyright © 2018 Courseware, All rights reservs</el-col>
          <el-col :span="8">
            <ul class="menu">
              <li class="item"><a href="#">Pricay</a></li>
              <li class="item"><a href="#">Terms</a></li>
              <li class="item"><a href="#">Sitecap</a></li>
            </ul>
          </el-col>
        </el-row>
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss">
@import "~assets/scss/variable";

.footer {
  .footer-top {
    background-color: $color-bg-light-black;
    .container {
      padding: 0;
      .el-col {
        padding: 0 15px;
      }
      .widget {
        display: inline-block;
        margin-bottom: 30px;
        padding-top: 32px;
        width: 100%;
        .footer-logo {
          display: block;
          margin-bottom: 45px;
          max-width: 180px;
        }
        .title {
          color: $color-normal;
          font-weight: 700;
          margin-bottom: 40px;
          font-size: 14px;
        }
        .detail {
          color: $color-text-header;
          p {
            font-size: 14px;
            font-weight: 400;
            line-height: 24px;
          }
          .footer-contacts {
            margin: 25px 0;
            li {
              font-size: 14px;
              padding: 5px 0;
              i {
                display: inline-block;
                vertical-align: middle;
                margin-right: 8px;
                font-size: 16px;
              }
              a {
                display: inline-block;
                vertical-align: middle;
                color: $color-text-header;
                &:hover {
                  color: $color-normal;
                }
              }
            }
          }
          .menu {
            .item {
              width: 100%;
              font-size: 16px;
              color: $color-text-header;
              line-height: 26px;
              padding-bottom: 13px;
              transition: all 0.25s ease;
              &:hover {
                padding-left: 7px;
                a {
                  color: $color-normal;
                }
              }
              a {
                color: $color-text-header;
                .icon {
                  margin-right: 5px;
                  font-size: 14px;
                  font-weight: 700;
                }
              }
            }
          }
        }
      }
    }
  }
  .footer-bottom {
    background-color: $color-bg-black;
    padding: 50px 0;
    .container {
      color: $color-text-header;
      font-size: 14px;
      .menu {
          text-align: right;
        li.item {
          margin-left: 20px;
          display: inline-block;
          vertical-align: middle;
          a {
            color: $color-text-header;
            transition: all 0.25s ease;
            &:hover {
                color: $color-normal;
            }
          }
        }
      }
    }
  }
}
</style>
