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
              <h2 class="section-title">强烈推荐</h2>
              <!-- <h2 class="section-title">Popular Courses</h2> -->
              <p>Donec rutrum congue leo eget malesuada</p>
            </div>
            <div class="right-content">
              <button><i class="el-icon-arrow-left swiper-button course-swiper-button-prev"></i></button>
              <button><i class="el-icon-arrow-right swiper-button course-swiper-button-next"></i></button>
            </div>
          </div>
          <div class="course-list">
            <div
              class="courses"
              v-swiper:courseSwiper="coursesSwiperOption"
              @someSwiperEvent="callback"
            >
              <div class="swiper-wrapper">
                <div
                  class="swiper-slide course-item"
                  v-for="item in popularCourses"
                  :key="`popularCourses_${item.id}`"
                >
                  <div class="wrapper">
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
                      <div class="price-rate">
                        <div class="price">
                          <span class="currency">￥</span>
                          <span class="num">{{item.price}}</span>
                        </div>
                        <div class="rate">
                          <span class="star">
                            <el-rate
                              v-model="item.rate"
                              :disabled="true"
                            ></el-rate>
                          </span>
                          <span class="num">{{item.rate}}</span>
                        </div>
                      </div>
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
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="hot-search bg-black">
      <div class="section-padding">
        <div class="container">
          <div class="top-content text-center">
            <h3 class="section-title">热门搜索</h3>
            <!-- <h3 class="section-title">HOT SEARCH</h3> -->
            <P>Donec rutrum congue leo eget malesuada</P>
          </div>
          <el-row class="courses">
            <el-col
              :span="8"
              class="left"
            >
              <div class="wrapper">
                <div
                  class="thumb"
                  :style="`background-image: url(${popularCourses[0].imgUrl});`"
                ></div>
                <div class="item-detail">
                  <div class="title-wrapper">
                    <a
                      href="##"
                      class="item-title"
                    >{{popularCourses[0].title}}</a>
                  </div>
                </div>
              </div>
            </el-col>
            <el-col
              :span="16"
              class="right"
            >
              <el-row class="right-top">
                <el-col :span="12">
                  <div class="wrapper">
                    <div
                      class="thumb"
                      :style="`background-image: url(${popularCourses[1].imgUrl});`"
                    ></div>
                    <div class="item-detail">
                      <div class="title-wrapper">
                        <a
                          href="##"
                          class="item-title"
                        >{{popularCourses[1].title}}</a>
                      </div>
                    </div>
                  </div>
                </el-col>
                <el-col :span="12">
                  <div class="wrapper">
                    <div
                      class="thumb"
                      :style="`background-image: url(${popularCourses[2].imgUrl});`"
                    ></div>
                    <div class="item-detail">
                      <div class="title-wrapper">
                        <a
                          href="##"
                          class="item-title"
                        >{{popularCourses[2].title}}</a>
                      </div>
                    </div>
                  </div>
                </el-col>
              </el-row>
              <div class="right-bottom">
                <div class="wrapper">
                  <div
                    class="thumb"
                    :style="`background-image: url(${popularCourses[3].imgUrl});`"
                  ></div>
                  <div class="item-detail">
                    <div class="title-wrapper">
                      <a
                        href="##"
                        class="item-title"
                      >{{popularCourses[3].title}}</a>
                    </div>
                  </div>
                </div>
              </div>
            </el-col>
          </el-row>
        </div>
      </div>
    </section>
    <section class="best-categories section-padding">
      <div class="container">
        <div class="top-content text-center">
          <h2 class="section-title">行业分类</h2>
          <p>Donec rutrum congue leo eget malesuada</p>
        </div>
        <div class="category-items">
          <div
            class="item radius text-center"
            v-for="category in categories"
            :key="`category_${category.id}`"
          >
            <div class="item-thumb"><img
                class="radius"
                :src="category.thumb"
                alt="Item Thumbnail"
              ></div>
            <div class="item-details">
              <a href="#">
                <div class="item-texts">
                  <i
                    :class="category.icon"
                    class="icon"
                  ></i>
                  <span class="item-title">{{category.title}}</span>
                </div>
              </a>
            </div>
          </div>
        </div>
        <div class="btn-container text-center">
          <a
            href="#"
            class="btn"
          >Browse all</a>
        </div>
      </div>
    </section>
    <section class="facts">
      <div class="overlay section-padding">
        <div class="container">
          <el-row>
            <el-col
              :span="6"
              v-for="item in facts"
              :key="`fact_${item.id}`"
            >
              <div class="item">
                <div
                  class="icon"
                  :class="item.icon"
                ></div>
                <div class="item-detail">
                  <div class="count">{{item.count}}</div>
                  <div class="title">{{item.title}}</div>
                </div>
              </div>
            </el-col>
          </el-row>
        </div>
      </div>
    </section>
    <section class="popular-courses">
      <div class="section-padding">
        <div class="container">
          <div class="top-content">
            <div class="left-content">
              <h2 class="section-title">培训课程</h2>
              <p>Donec rutrum congue leo eget malesuada</p>
            </div>
            <div class="right-content">
              <button><i class="el-icon-arrow-left swiper-button peixun-swiper-button-prev"></i></button>
              <button><i class="el-icon-arrow-right swiper-button peixun-swiper-button-next"></i></button>
            </div>
          </div>
          <div class="course-list">
            <div
              class="courses"
              v-swiper:peixunSwiper="peixunSwiperOption"
              @someSwiperEvent="callback"
            >
              <div class="swiper-wrapper">
                <div
                  class="swiper-slide course-item"
                  v-for="item in popularCourses"
                  :key="`popularCourses_${item.id}`"
                >
                  <div class="wrapper">
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
                      <div class="price-rate">
                        <div class="price">
                          <span class="currency">￥</span>
                          <span class="num">{{item.price}}</span>
                        </div>
                        <div class="rate">
                          <span class="star">
                            <el-rate
                              v-model="item.rate"
                              :disabled="true"
                            ></el-rate>
                          </span>
                          <span class="num">{{item.rate}}</span>
                        </div>
                      </div>
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
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="blog-posts bg-black">
      <div class="section-padding">
        <div class="container">
          <div class="top-content">
            <div class="left-content">
              <!-- <h2 class="section-title">RECENT BLOG POSTS</h2> -->
              <h2 class="section-title">精选口碑</h2>
              <p>Donec rutrum congue leo eget malesuada</p>
            </div>
            <div class="right-content">
              <button><i class="el-icon-arrow-left swiper-button post-swiper-button-prev"></i></button>
              <button><i class="el-icon-arrow-right swiper-button post-swiper-button-next"></i></button>
            </div>
          </div>
          <div
            class="posts"
            v-swiper:postSwiper="postsSwiperOption"
            @someSwiperEvent="callback"
          >
            <div class="swiper-wrapper">
              <div
                class="swiper-slide post-item"
                v-for="post in posts"
                :key="`post_${post.id}`"
              >
                <img
                  :src="post.thumb"
                  class="thumb radius"
                  alt=""
                >
                <div class="item-detail">
                  <h3 class="title">{{post.title}}</h3>
                  <div class="meta">
                    <div class="author">
                      <i class="icon el-icon-service"></i>
                      <span>{{post.author}}</span>
                    </div>
                    <div class="date">
                      <i class="icon el-icon-date"></i>
                      <span>{{post.date}}</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="sponsers text-center">
      <div class="section-padding">
        <div class="container">
          <div
            v-swiper:sponserSwiper="sponsersSwiperOption"
            @someSwiperEvent="callback"
          >
            <div class="swiper-wrapper">
              <div
                class="swiper-slide sponser-item"
                v-for="sponser in sponsers"
                :key="`sponser_${sponser.id}`"
              >
                <div>
                  <div class="top">
                    <img
                      :src="sponser.thumb"
                      class="thumb rounded-circle"
                      alt=""
                    >
                    <span class="name">{{sponser.name}}</span>
                  </div>
                  <div class="sponser-detail">{{sponser.desc}}</div>
                </div>
              </div>
            </div>
            <div class="swiper-pagination"></div>
            <div
              class="swiper-button-prev"
              slot="button-prev"
            ></div>
            <div
              class="swiper-button-next"
              slot="button-next"
            ></div>
          </div>
        </div>
      </div>
    </section>
    <section class="subscribe text-center">
      <div class="section-padding">
        <div class="container">
          <!-- <h3 class="title">Subscribe Weekly Newsletter</h3> -->
          <h3 class="title">Newsletter订阅</h3>
          <div class="form">
            <input
              type="text"
              placeholder="Enter Email Address Here"
            >
            <button class="form-btn">Subscribe now</button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
require("swiper/dist/css/swiper.css");

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
          price: "16.99",
          rate: 3,
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/1.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/1.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        },
        {
          id: 2,
          imgUrl: require("../assets/img/popular/2.jpg"),
          title: "Complete JavaScript Course 2018: Build Real Projects!",
          price: "16.99",
          rate: 3,
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/2.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/2.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        },
        {
          id: 3,
          imgUrl: require("../assets/img/popular/3.jpg"),
          title: "Complete JavaScript Course 2018: Build Real Projects!",
          price: "16.99",
          rate: 3,
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/3.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/3.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        },
        {
          id: 4,
          imgUrl: require("../assets/img/popular/4.jpg"),
          title: "Complete JavaScript Course 2018: Build Real Projects!",
          price: "16.99",
          rate: 3,
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/4.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/4.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        },
        {
          id: 5,
          imgUrl: require("../assets/img/popular/5.jpg"),
          title: "Complete JavaScript Course 2018: Build Real Projects!",
          price: "16.99",
          rate: 3,
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/5.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/5.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        },
        {
          id: 6,
          imgUrl: require("../assets/img/popular/6.jpg"),
          title: "Complete JavaScript Course 2018: Build Real Projects!",
          price: "16.99",
          rate: 3,
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/6.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/6.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        },
        {
          id: 7,
          imgUrl: require("../assets/img/popular/7.jpg"),
          title: "Complete JavaScript Course 2018: Build Real Projects!",
          price: "16.99",
          rate: 3,
          instructor: "Justin Marks",
          avatar: require("../assets/img/avatar/7.png"),
          date: "2018-08-30",
          city: "北京",
          sponsor: {
            thumb: require("../assets/img/avatar/7.png"),
            name: "阿里巴巴"
          },
          viewTime: 10
        }
      ],
      categories: [
        {
          id: 1,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/1.jpg")
        },
        {
          id: 2,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/2.jpg")
        },
        {
          id: 3,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/3.jpg")
        },
        {
          id: 4,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/4.jpg")
        },
        {
          id: 5,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/5.jpg")
        },
        {
          id: 6,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/6.jpg")
        },
        {
          id: 7,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/7.jpg")
        },
        {
          id: 8,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/8.jpg")
        },
        {
          id: 9,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/9.jpg")
        },
        {
          id: 10,
          icon: "el-icon-goods",
          title: "DESIGN",
          thumb: require("../assets/img/category/10.jpg")
        }
      ],
      facts: [
        {
          id: 1,
          icon: "el-icon-picture",
          count: 788,
          title: "EXPERT INSTRUCTORS"
        },
        {
          id: 2,
          icon: "el-icon-edit-outline",
          count: 788,
          title: "EXPERT INSTRUCTORS"
        },
        {
          id: 3,
          icon: "el-icon-menu",
          count: 788,
          title: "EXPERT INSTRUCTORS"
        },
        {
          id: 4,
          icon: "el-icon-star-on",
          count: 788,
          title: "EXPERT INSTRUCTORS"
        }
      ],
      posts: [
        {
          id: 1,
          thumb: require("../assets/img/posts/4.jpg"),
          title: "ow To Create A Local Business Directory Site In WordPress",
          author: "Anthony Doe",
          date: "2018-07-08"
        },
        {
          id: 2,
          thumb: require("../assets/img/posts/5.jpg"),
          title: "ow To Create A Local Business Directory Site In WordPress",
          author: "Anthony Doe",
          date: "2018-07-08"
        },
        {
          id: 3,
          thumb: require("../assets/img/posts/6.jpg"),
          title: "ow To Create A Local Business Directory Site In WordPress",
          author: "Anthony Doe",
          date: "2018-07-08"
        },
        {
          id: 4,
          thumb: require("../assets/img/posts/7.jpg"),
          title: "ow To Create A Local Business Directory Site In WordPress",
          author: "Anthony Doe",
          date: "2018-07-08"
        },
        {
          id: 5,
          thumb: require("../assets/img/posts/8.jpg"),
          title: "ow To Create A Local Business Directory Site In WordPress",
          author: "Anthony Doe",
          date: "2018-07-08"
        }
      ],
      sponsers: [
        {
          id: 1,
          name: "阿里巴巴",
          thumb: require("../assets/img/avatar/1.png"),
          desc:
            "A collection of textile samples lay spread out on the table. Samsa was a travelling salesman and above it there hung a picture that he had recently cut out of an illustrated magazine and housed in a nice, gilded frame."
        },
        {
          id: 2,
          name: "百度",
          thumb: require("../assets/img/avatar/2.png"),
          desc:
            "A collection of textile samples lay spread out on the table. Samsa was a travelling salesman and above it there hung a picture that he had recently cut out of an illustrated magazine and housed in a nice, gilded frame."
        },
        {
          id: 3,
          name: "腾讯",
          thumb: require("../assets/img/avatar/3.png"),
          desc:
            "A collection of textile samples lay spread out on the table. Samsa was a travelling salesman and above it there hung a picture that he had recently cut out of an illustrated magazine and housed in a nice, gilded frame."
        },
        {
          id: 4,
          name: "今日头条",
          thumb: require("../assets/img/avatar/4.png"),
          desc:
            "A collection of textile samples lay spread out on the table. Samsa was a travelling salesman and above it there hung a picture that he had recently cut out of an illustrated magazine and housed in a nice, gilded frame."
        },
        {
          id: 5,
          name: "滴滴",
          thumb: require("../assets/img/avatar/5.png"),
          desc:
            "A collection of textile samples lay spread out on the table. Samsa was a travelling salesman and above it there hung a picture that he had recently cut out of an illustrated magazine and housed in a nice, gilded frame."
        }
      ],
      coursesSwiperOption: {
        slidesPerView: 4,
        autoplay: true,
        simulateTouch: true,
        navigation: {
          nextEl: ".course-swiper-button-next",
          prevEl: ".course-swiper-button-prev"
        }
      },
      peixunSwiperOption: {
        slidesPerView: 4,
        autoplay: true,
        simulateTouch: true,
        navigation: {
          nextEl: ".peixun-swiper-button-next",
          prevEl: ".peixun-swiper-button-prev"
        }
      },
      postsSwiperOption: {
        slidesPerView: 3,
        autoplay: true,
        simulateTouch: true,
        navigation: {
          nextEl: ".post-swiper-button-next",
          prevEl: ".post-swiper-button-prev"
        }
      },
      sponsersSwiperOption: {
        autoplay: true,
        simulateTouch: true,
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev"
        },
        pagination: {
          el: ".swiper-pagination"
        }
      }
    };
  },
  methods: {
    callback() {}
  },
  mounted() {
    //   setTimeout(() => {
    //     this.banners.push('/4.jpg')
    //     console.log('banners update')
    //   }, 3000)
    //   console.log(
    //     'This is current swiper instance object', this.mySwiper,
    //     'It will slideTo banners 3')
    // this.mySwiper.slideTo(3, 1000, false);
  }
};
</script>
<style lang="scss">
@import "~assets/scss/variable";
.top-content {
  display: inline-block;
  margin-bottom: 4.7em;
  width: 100%;
  p {
    color: $color-text-label;
    font-size: 1.125em;
    font-weight: 600;
    line-height: 1.4;
    margin: 0;
  }
  .left-content {
    float: left;
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
      height: 35px;
      > i {
        background-color: $color-bg-btn-disable;
        border-radius: 4px;
        color: #455a64;
        font-weight: 700;
        display: inline-block;
        font-size: 20px;
        height: 35px;
        width: 35px;
        line-height: 35px;
        text-align: center;
        margin: 0;
        &.swiper-button {
          outline: none;
          position: static;
          background-image: none;
        }
      }
    }
  }
}
.btn {
  line-height: 60px;
  padding: 0 45px;
  background: $color-blue;
  color: $color-normal;
  font-size: 14px;
  letter-spacing: 0.5px;
  cursor: pointer;
  border: none;
  border-radius: 5px;
  display: inline-block;
  font-weight: 700;
  text-transform: uppercase;
  margin-top: 8px;
  transition: all 0.3s cubic-bezier(0.55, 0, 0.5, 1);
  &:hover {
    background: rgba(13, 71, 161, 0.7);
    font-size: 16px;
  }
}
.section-padding {
  padding: 7.125em 0;
}

.home {
  .carousel {
    .banner {
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
      .overlay {
        width: 100%;
        height: 100%;
        background: $color-bg-overlay;
        overflow: hidden;
        .container {
          text-align: center;
          margin-top: 200px;
          .sub-title {
            text-transform: uppercase;
            font-size: 1.875em;
            font-weight: 700;
            color: $color-normal;
            margin-bottom: 0.85rem;
          }
          .banner-title {
            font-size: 5em;
            color: $color-normal;
            font-weight: 900;
            margin: 0;
            text-transform: uppercase;
            margin-bottom: 3rem;
          }
        }
      }
    }
  }
  .popular-courses {
    background-color: $color-normal;
    .section-padding {
      padding: 7.125em 0 6.6em;
      .container {
        .top-content {
          display: inline-block;
          margin-bottom: 4.7em;
          width: 100%;
        }
        .course-list {
          .courses {
            white-space: nowrap;
            overflow: hidden;
            border-radius: 5px;
            .course-item {
              display: inline-block;
              white-space: normal;
              position: relative;
              width: 100%;
              text-align: center;
              .wrapper {
                display: inline-block;
                width: 270px;
              }
              // 22.5
              // 11.25
              // 30
              &.swiper-slide-active {
                text-align: left;
                & + .course-item {
                  margin-left: -3.75px;
                  & + .course-item {
                    margin-right: -3.75rpx;
                    & + .course-item {
                      text-align: right;
                    }
                  }
                }
              }
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
                bottom: 224px;
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
                    color: $color-text-label;
                  }
                }
              }
              .item-detail {
                border: 1px solid $color-border-gray;
                border-radius: 0 0 5px 5px;
                padding: 32px 0 0;
                > .title {
                  color: $color-text-black;
                  display: inline-block;
                  font-size: 16px;
                  font-weight: 700;
                  letter-spacing: -0.01px;
                  line-height: 1.4;
                  margin: 4px 0;
                  padding: 0 1.25em;

                  > a {
                    color: $color-text-black;
                  }
                }
                .price-rate {
                  padding: 0 1.25em;
                  display: inline-block;
                  margin: 12px 0 15px;
                  width: 100%;
                  .price {
                    float: left;
                    color: $color-blue;
                    font-size: 18px;
                    font-weight: 700;
                  }
                  .rate {
                    float: right;
                    .star {
                      display: inline-block;
                      vertical-align: middle;
                    }
                    .num {
                      display: inline-block;
                      vertical-align: middle;
                      color: $color-text-black;
                      font-size: 14px;
                      font-weight: 700;
                    }
                  }
                }
                > .label {
                  display: inline-block;
                  margin-bottom: 10px;
                  padding: 0 1.25em;
                  width: 100%;
                  color: $color-text-label;
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
                  border-top: 1px solid $color-border-gray;
                  color: $color-text-label;
                  font-size: 12px;
                  padding: 0 1.25em;
                  line-height: 55px;
                  padding-bottom: 5px;
                  font-weight: 600;
                  text-align: left;
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
                      color: $color-text-label;
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
  .hot-search {
    .section-padding {
      .container {
        .courses {
          height: 630px;
          margin-bottom: 30px;
          .el-col {
            height: 100%;
          }
          .wrapper {
            height: 100%;
            border-radius: 5px;
            overflow: hidden;
            position: relative;
            &:hover {
              .thumb {
                transform: scale(1.1);
              }
            }
            .thumb {
              height: 100%;
              background-size: cover;
              background-repeat: no-repeat;
              background-position: center;
              transition: all 0.75s cubic-bezier(0.55, 0, 0.5, 1);
            }
            .item-detail {
              position: absolute;
              left: 0;
              right: 0;
              top: 0;
              bottom: 0;
              z-index: 2;
              .title-wrapper {
                height: 100%;
                display: flex;
                align-items: center;
                justify-content: center;
                font-size: 1.375em;
                line-height: 1.3;
                padding: 2em;
                text-align: center;
                .item-title {
                  text-transform: uppercase;
                  color: $color-normal;
                  background-color: $color-bg-overlay;
                  padding: 10px;
                  border-radius: 5px;
                  max-width: 90%;
                }
              }
            }
          }
          .left {
            padding-right: 15px;
          }
          .right {
            padding-left: 15px;
            .right-top {
              height: 300px;
              margin-bottom: 30px;
              .el-col {
                padding-right: 15px;
              }
              .el-col:last-child {
                padding-left: 15px;
                padding-right: 0;
              }
            }
            .right-bottom {
              height: 300px;
            }
          }
        }
      }
    }
  }
  .best-categories {
    .category-items {
      display: flex;
      flex-wrap: wrap;
      align-content: space-between;
      margin: 0 -8px;
      .item {
        overflow: hidden;
        position: relative;
        margin: 15px 8px;
        width: 18.55%;
        cursor: pointer;
        .item-thumb {
          img {
            display: block;
            width: 100%;
          }
        }
        &:hover {
          .item-details {
            top: 0%;
          }
        }
        .item-details {
          background: rgba(37, 32, 55, 0.6);
          height: 100%;
          width: 100%;
          left: 0;
          top: 100%;
          position: absolute;
          transition: all 0.45s cubic-bezier(0.55, 0, 0.5, 1);
          > a {
            color: $color-normal;
            display: flex;
            box-pack: center;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            font-weight: 700;
            height: 100%;
            width: 100%;
            text-transform: uppercase;
            .item-texts {
              padding: 0 15px;
              width: 100%;
              .icon {
                color: #fff;
                display: inline-block;
                font-size: 32px;
                margin-bottom: 13px;
                width: 100%;
              }
            }
          }
        }
      }
    }
    .btn-container {
      padding-top: 4.625em;
      margin-bottom: 8px;
      .btn:hover {
        transform: scale(1) !important;
      }
    }
  } 
  .facts {
    background: url("../assets/img/bg/bg2.jpg") center no-repeat;
    background-size: cover;
    .overlay {
      background-color: rgba($color: $color-blue, $alpha: 0.9);
      .container {
        color: $color-normal;
        .item {
          font-size: 0;
          .icon {
            display: inline-block;
            vertical-align: top;
            margin-right: 15px;
            font-size: 55px;
          }
          .item-detail {
            display: inline-block;
            vertical-align: center;
            .count {
              font-size: 50px;
              font-weight: 300;
              font-family: "Source Sans Pro", sans-serif;
            }
            .title {
              font-size: 16px;
              margin-top: 13px;
              text-transform: uppercase;
              font-weight: 700;
            }
          }
        }
      }
    }
  }
  .blog-posts {
    .posts.swiper-container {
      width: 100%;
      overflow: hidden;
      .post-item {
        padding: 0 10px;
        &.swiper-slide-active {
          padding-left: 0;
          padding-right: 20px;
          & + .post-item + .post-item {
            padding-right: 0;
            padding-left: 20px;
          }
        }
        .thumb {
          display: block;
          width: 100%;
          max-width: 370px;
          max-height: 192px;
        }
        .item-detail {
          .title {
            margin: 16px 0 8px;
            font-size: 22px;
            line-height: 1.4;
            color: $color-normal;
            font-weight: 600;
          }
          .meta {
            margin-top: 16px;
            color: $color-text-label;
            font-weight: 300;
            font-size: 14px;
            .icon {
              padding-right: 8px;
            }
            span {
            }
            .author {
              margin-right: 30px;
            }
            .author,
            .date {
              display: inline-block;
              vertical-align: middle;
            }
          }
        }
      }
    }
  }
  .sponsers {
    .swiper-wrapper {
      padding-bottom: 80px;
    }
    .swiper-pagination {
      bottom: 40px;
    }
    .sponser-item {
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 0 15%;
      .top {
        .thumb {
          display: inline-block;
          vertical-align: middle;
          width: 90px;
          height: 90px;
        }
        .name {
          margin-left: 20px;
          display: inline-block;
          vertical-align: middle;
          font-size: 16px;
          color: $color-text-black;
          font-weight: 600;
        }
      }
      .sponser-detail {
        margin-top: 40px;
        font-size: 16px;
        color: $color-text-label;
      }
    }
  }
  .subscribe {
    background-color: $color-bg-gray;
    .title {
      font-size: 22px;
      font-weight: 700;
      margin-bottom: 8px;
    }
    .form {
      display: inline-block;
      max-width: 770px;
      margin: 3em auto 0.4em;
      width: 100%;
      > input {
        background: #eaedef;
        border: 1px solid #d0d5d8;
        border-radius: 5px 0 0 5px;
        color: #90a4ae;
        float: left;
        font-size: 0.875em;
        font-weight: 700;
        margin: 0;
        padding: 1.95% 3% 1.95% 3%;
        width: 74%;
        outline: none;
        line-height: 28px;
      }
      > button {
        line-height: 28px;
        outline: none;
        background: #0d47a1;
        border: 1px solid #0d47a1;
        border-radius: 0 5px 5px 0;
        color: #fff;
        cursor: pointer;
        float: right;
        font-size: 12px;
        font-weight: 700;
        padding: 1.95% 5% 1.95% 5%;
        text-align: center;
        text-transform: uppercase;
        width: 26%;
      }
    }
  }
}
</style>
