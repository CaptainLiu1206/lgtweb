<template>
  <div class="home">
    <section class="carousel">
      <el-carousel
        :interval="5000"
        height="600px"
        indicator-position="none"
      >
        <el-carousel-item
          class="banner"
          :style="`background-image: url(${banner.url});`"
          v-for="banner in banners"
          :key="`banner_${banner.id}`"
        >
          <div class="overlay">
            <div class="container">
              <h6 class="sub-title">{{banner.subTitle}}</h6>
              <h2 class="banner-title">{{banner.title}}</h2>
              <a
                href="#"
                class="btn"
              >GET STARTED</a>
            </div>
          </div>
        </el-carousel-item>
      </el-carousel>
    </section>
    <section class="popular-courses">
      <div class="section-padding">
        <div class="container">
          <div class="top-content">
            <div class="left-content">
              <h2 class="section-title">Popular Courses</h2>
              <p>Donec rutrum congue leo eget malesuada</p>
            </div>
            <div class="right-content">
              <button><i class="el-icon-arrow-left"></i></button>
              <button><i class="el-icon-arrow-right"></i></button>
            </div>
          </div>
          <div class="course-list">
            <ul class="courses">
              <li
                class="course-item"
                v-for="item in popularCourses"
                :key="`popularCourses_${item.id}`"
              >
                <div class="img-wrapper">
                  <img
                    class="course-thumb"
                    :src="item.imgUrl"
                    alt=""
                  >
                </div>
                <div class="avatar">
                  <img
                    :src="item.avatar"
                    alt=""
                    class="rounded-circle"
                  >
                  <h4 class="instructor">
                    <a href="">{{item.instructor}}</a>
                  </h4>
                </div>
                <div class="item-detail">
                  <h3 class="title">
                    <a href="">{{item.title}}</a>
                  </h3>
                  <div class="label">
                    <span class="date">{{item.date}}</span>
                    <span class="city">{{item.city}}</span>
                  </div>
                  <div class="meta">
                    <a
                      href=""
                      class="sponsor"
                    >
                      <div class="thumb-wrapper">
                        <img
                          :src="item.sponsor.thumb"
                          class="rounded-circle"
                          alt=""
                        >
                      </div>
                      <a class="name">{{item.sponsor.name}}</a>
                    </a>
                    <div class="view">
                      <i class="icon el-icon-view"></i>
                      <span class="times">{{item.viewTime}}</span>
                    </div>
                  </div>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>

export default {
  name: "Home",
  asyncData({ store, route }) {},
  title() {
    return "home1";
  },
  data() {
    return {
      pagename: "home page",
      banners: [
        {
          id: 1,
          url: require("../assets/img/banner/1.jpg"),
          subTitle: "TAKE THE WORLD’S BEST COURSES",
          title: "LEARN WITH US"
        },
        {
          id: 2,
          url: require("../assets/img/banner/2.jpg"),
          subTitle: "TAKE THE WORLD’S BEST COURSES",
          title: "LEARN WITH US"
        },
        {
          id: 3,
          url: require("../assets/img/banner/3.jpg"),
          subTitle: "TAKE THE WORLD’S BEST COURSES",
          title: "LEARN WITH US"
        },
        {
          id: 4,
          url: require("../assets/img/banner/4.jpg"),
          subTitle: "TAKE THE WORLD’S BEST COURSES",
          title: "LEARN WITH US"
        }
      ],
      popularCourses: [
        {
          id: 1,
          imgUrl: require("../assets/img/popular/1.jpg"),
          title: "Complete JavaScript Course 2018: Build Real Projects!",
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/1.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/1.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        }
      ]
    };
  }
};
</script>
<style lang="scss">
.home {
  .carousel {
    .banner {
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
      .overlay {
        width: 100%;
        height: 100%;
        background: rgba(27, 28, 35, 0.75);
        overflow: hidden;
        .container {
          text-align: center;
          margin-top: 200px;
          .sub-title {
            text-transform: uppercase;
            font-size: 1.875em;
            font-weight: 700;
            color: #fff;
            margin-bottom: 0.85rem;
          }
          .banner-title {
            font-size: 5em;
            color: #fff;
            font-weight: 900;
            margin: 0;
            text-transform: uppercase;
            margin-bottom: 3rem;
          }
          .btn {
            line-height: 3.75em;
            padding: 0 2.8125em;
            background: #0d47a1;
            color: #fff;
            font-size: 0.875em;
            letter-spacing: 0.5px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            display: inline-block;
            font-weight: 700;
            text-transform: uppercase;
            margin-top: 0.5rem;
            transition: all 0.3s cubic-bezier(0.55, 0, 0.5, 1);
            &:hover {
              background: rgba(13, 71, 161, 0.7);
              font-size: 1em;
            }
          }
        }
      }
    }
  }
  .popular-courses {
    background-color: #fff;
    .section-padding {
      padding: 7.125em 0 6.6em;
      .container {
        .top-content {
          display: inline-block;
          margin-bottom: 4.7em;
          width: 100%;
          .left-content {
            float: left;
            .section-title {
              color: #37474f;
              font-size: 1.5625rem;
              margin: 0 0 7px;
              font-weight: 900;
              text-transform: uppercase;
            }
            p {
              color: #90a4ae;
              font-size: 1.125em;
              font-weight: 600;
              line-height: 1.4;
              margin: 0;
            }
          }
          .right-content {
            float: right;
            padding-top: 12px;
            button {
              background-color: transparent;
              border: none;
              outline: none;
              box-shadow: none;
              cursor: pointer;
              margin-left: 5px;
              padding: 0;
              > i {
                background-color: #eceff1 !important;
                border-radius: 4px;
                color: #455a64;
                display: inline-block;
                font-size: 20px;
                height: 35px;
                width: 35px;
                line-height: 35px;
                text-align: center;
              }
            }
          }
        }
        .course-list {
          .courses {
            .course-item {
              position: relative;
              width: 270px;
              margin-right: 30px;
              .img-wrapper {
                width: 100%;
                overflow: hidden;
                border-top-left-radius: 5px;
                border-top-right-radius: 5px;
                .course-thumb {
                  display: block;
                  width: 100%;
                  transition: all 0.3s ease-in;
                  &:hover {
                    opacity: 0.8;
                    transform: scale(1.18);
                  }
                }
              }
              .avatar {
                position: absolute;
                bottom: 184px;
                left: 20px;
                right: 20px;
                z-index: 111;
                margin-bottom: -22.5px;
                img {
                  float: left;
                  width: 45px;
                  height: 45px;
                }
                > .instructor {
                  float: left;
                  line-height: 45px;
                  margin-left: 30px;
                  font-size: 22px;
                  > a {
                      color: #90a4ae;
                  }
                }
              }
              .item-detail {
                border: 1px solid #cfd8dc;
                border-radius: 0 0 5px 5px;
                padding: 32px 0 0;
                > .title {
                  color: #37474f;
                  display: inline-block;
                  font-size: 16px;
                  font-weight: 700;
                  letter-spacing: -0.01px;
                  line-height: 1.4;
                  margin: 4px 0;
                  padding: 0 1.25em;
                  > a {
                    color: #37474f;
                  }
                }
                > .label {
                  display: inline-block;
                  margin: 10px 0;
                  padding: 0 1.25em;
                  width: 100%;
                  color: #90a4ae;
                  font-size: 0.875em;
                  font-weight: 600;
                  .date {
                    float: left;
                  }
                  .city {
                    float: right;
                  }
                }
                > .meta {
                  border-top: 1px solid #cfd8dc;
                  color: #90a4ae;
                  font-size: 12px;
                  padding: 0 1.25em;
                  line-height: 55px;
                  padding-bottom: 5px;
                  font-weight: 600;
                  .sponsor {
                    .thumb-wrapper {
                      display: inline-block;
                      vertical-align: middle;
                      > img {
                        display: block;
                        width: 26px;
                        height: 26px;
                      }
                    }

                    > .name {
                      display: inline-block;
                      vertical-align: middle;
                      margin-left: 5px;
                      color: #90a4ae;
                    }
                  }
                  .view {
                    float: right;
                    font-size: 14px;
                    .icon {
                      margin-right: 5px;
                      font-size: 16px;
                    }
                  }
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
