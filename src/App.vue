<template>
  <div id="app">
    <Header />
    <transition name="fade" mode="out-in">
      <router-view class="view"></router-view>
    </transition>
    <Footer />
  </div>
</template>

<script>
import Header from './layout/Header'
import Footer from './layout/Footer'
export default {
  components: {
    Header,
    Footer
  }
}
</script>


<style lang="scss">
.fade-enter-active, .fade-leave-active {
  transition: all .2s ease;
}

.fade-enter, .fade-leave-active {
  opacity: 0;
}
</style>
