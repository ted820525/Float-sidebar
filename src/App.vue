<template>
  <div id="app">
    <nav>
      <div class="menu">
        <div>{{page}}</div>
        <i @click="show = !show " class="fas fa-bars"></i>
      </div>
      <transition-group name="fade" tag="ul">
        <li key="close" v-show="show" @click="show = !show ">
          <i class="fas fa-times"></i>
        </li>
        <li key="1" v-show="show" @click="togglePage('Youtube')">
          <i class="fab fa-youtube"></i>
        </li>
        <li key="2" v-show="show" @click="togglePage('Twitter')">
          <i class="fab fa-twitter"></i>
        </li>
        <li key="3" v-show="show" @click="togglePage('Pinterest')">
          <i class="fab fa-pinterest"></i>
        </li>
        <li key="4" v-show="show" @click="togglePage('Facebook')">
          <i class="fab fa-facebook"></i>
        </li>
        <li key="5" v-show="show" @click="togglePage('Instagram')">
          <i class="fab fa-instagram"></i>
        </li>
        <li key="sidebar" v-show="show"></li>
      </transition-group>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      page: "Youtube"
    };
  },
  methods: {
    togglePage(page) {
      this.show = !this.show;
      this.page = page;
    }
  },
  name: "App"
};
</script>

<style lang="scss" scoped>
@import url("https://use.fontawesome.com/releases/v5.7.2/css/all.css");

nav {
  .menu {
    padding: 10px 20px 0;
    width: cals(100% -40px);
    height: 49px;
    border-bottom: 1px solid #efefef;
    background-color: rgba($color: #333, $alpha: 0.5);
    div {
      float: right;
    }
  }
  ul {
    position: absolute;
    top: 0px;
    left: -60px;
    padding: 0px;
    margin: 0px;
    height: 100vh;
    list-style: none;
    li {
      display: flex;
      justify-content: flex-end;
      align-items: center;
      width: 120px;
      height: 59px;
      border-bottom: 1px solid #555;
      background-color: #333;
      color: #fff;

      i {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 60px;
        height: 59px;
      }
    }
    li:last-child {
      height: calc(100% - 360px);
      border-bottom: none;
      background-color: rgba($color: #333, $alpha: 0.8);
    }
  }
}
@mixin ul-childs($values...) {
  @each $var in $values {
    &:nth-child(#{$var}) {
      transition: transform linear calc(0.1s * #{$var}), display 0.7s;
    }
  }
}
.fade-enter-active,
.fade-leave-active {
  @include ul-childs(1, 2, 3, 4, 5, 6, 7);
}
.fade-enter,
.fade-leave-to {
  transform: rotateY(-90deg);
}
</style>>