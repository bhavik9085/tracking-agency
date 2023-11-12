<template>
  <div class="loaderContainer" v-if="loader">
    <div class="loaderMain">
      <h5>Let me Finish up a little</h5>
      <div class="loader">
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
      </div>
      <h5>So, I can provide you with my best😉</h5>
    </div>
  </div>
  <div class="container">
    <nav>
      <div class="content">
        <div class="logo" @click="scroll">
          <img src="@/assets/img/Logo.png" alt="" />
          <div class="name">
            <span>LOSANGELES</span>
            <span>MOUNTAINS</span>
          </div>
        </div>
        <div class="navigations">
          <a
            href="#history"
            @click="tabSelected = 'history'"
            :class="{ selected: tabSelected == 'history' }"
            v-smooth-scroll="{
              duration: 2000,
              offset: navHeight * -1,
              updateHistory: false,
            }"
            >01. HISTORY</a
          >
          <a
            href="#team"
            @click="tabSelected = 'team'"
            :class="{ selected: tabSelected == 'team' }"
            v-smooth-scroll="{
              duration: 2000,
              offset: navHeight * -1,
              updateHistory: false,
            }"
            >02. TEAM</a
          >
        </div>
      </div>
    </nav>
    <div id="hero"></div>
    <section class="hero">
      <img src="@/assets/img/layer.png" alt="" />
    </section>
    <div class="button" id="button">
      <div class="content">
        <div class="navigations">
          <a href="#" class="linkhistory" @click="mobNav('history')"
            >01. HISTORY</a
          >
          <a href="#" class="linkteam" @click="mobNav('team')">02. TEAM</a>
        </div>
      </div>
    </div>
    <div id="history"></div>
    <div class="mobDiv">
      <section class="history">
        <div class="mainImage">
          <div
            class="img selected"
            :style="{
              'background-image':
                'url(' + require('@/assets/img/carousel1.jpg') + ')',
            }"
          ></div>
          <div
            class="img"
            :style="{
              'background-image':
                'url(' + require('@/assets/img/carousel2.jpg') + ')',
            }"
          ></div>
          <div
            class="img"
            :style="{
              'background-image':
                'url(' + require('@/assets/img/carousel3.jpg') + ')',
            }"
          ></div>
          <div
            class="img"
            :style="{
              'background-image':
                'url(' + require('@/assets/img/carousel4.jpg') + ')',
            }"
          ></div>
        </div>
        <div class="controls">
          <div class="control selected" @click="sliderControl(1)">
            <img src="@/assets/img/carousel1.jpg" alt="" />
          </div>
          <div class="control" @click="sliderControl(2)">
            <img src="@/assets/img/carousel2.jpg" alt="" />
          </div>
          <div class="control" @click="sliderControl(3)">
            <img src="@/assets/img/carousel3.jpg" alt="" />
          </div>
          <div class="control" @click="sliderControl(4)">
            <img src="@/assets/img/carousel4.jpg" alt="" />
          </div>
        </div>
        <div class="mainContent">
          <div class="content">
            <div class="number">
              <h1>01</h1>
              <div>
                <h2>HISTORY</h2>
                <h1>.</h1>
              </div>
            </div>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin in
              ante viverra, rutrum erat rutrum, consectetur mi. Proin at maximus
              est. Nullam purus ex, iaculis sed erat sed, blandit tincidunt
              quam. Cras scelerisque id quam sed dignissim Pellentesque urna
              nunc, gravida quis hendrerit ac, tristique ut quam. Vivamus
              suscipit dignissim tortor nec congue.
            </p>
          </div>
        </div>
      </section>
      <section class="team" id="team">
        <div class="mainContent">
          <div class="content">
            <div class="number">
              <h1>02</h1>
              <div>
                <h2>CLIMB</h2>
                <h1>.</h1>
              </div>
            </div>
            <p>
              Cras scelerisque id quam sed dignissim Pellentesque urna nunc,
              gravida quis hendrerit ac, tristique ut quam. Vivamus suscipit
              dignissim tortor nec congue.
            </p>
          </div>
        </div>
        <div class="teamNav">
          <div class="content">
            <span
              @click="mountain = 'mountain1'"
              :class="{ selected: mountain == 'mountain1' }"
              >MOUNTAIN 1</span
            >
            <span
              @click="mountain = 'mountain2'"
              :class="{ selected: mountain == 'mountain2' }"
              >MOUNTAIN 2</span
            >
          </div>
        </div>
        <div class="slider">
          <Transition name="mountain1">
            <div class="mountain1" v-if="mountain == 'mountain1'">
              <!-- <img src="@/assets/img/slider1.png" alt="" /> -->
              <div class="content">
                <div class="table">
                  <h4>SCHEDULE</h4>
                  <div>
                    <ul>
                      <li>
                        <span class="date">10 Apr 2023</span
                        ><span class="name">Vestibulum viverra</span>
                      </li>
                      <li>
                        <span class="date">11 Apr 2023</span
                        ><span class="name">Vestibulum viverra</span>
                      </li>
                      <li>
                        <span class="date">12 Apr 2023</span
                        ><span class="name">Vestibulum viverra</span>
                      </li>
                      <li>
                        <span class="date">13 Apr 2023</span
                        ><span class="name">Vestibulum viverra</span>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </Transition>
          <Transition name="mountain2">
            <div class="mountain2" v-if="mountain == 'mountain2'">
              <div class="content">
                <div class="table">
                  <h4>SCHEDULE</h4>
                  <div>
                    <ul>
                      <li>
                        <span class="date">14 Apr 2023</span
                        ><span class="name">Mestibulum miverra</span>
                      </li>
                      <li>
                        <span class="date">15 Apr 2023</span
                        ><span class="name">Mestibulum miverra</span>
                      </li>
                      <li>
                        <span class="date">16 Apr 2023</span
                        ><span class="name">Mestibulum miverra</span>
                      </li>
                      <li>
                        <span class="date">17 Apr 2023</span
                        ><span class="name">Mestibulum miverra</span>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </Transition>
        </div>
        <footer>
          <div class="content">
            <div class="logo">
              <span>
                <img src="@/assets/img/Logo.png" alt="" />
              </span>
              <div class="name">
                <span>LOSANGELES</span>
                <span>MOUNTAINS</span>
              </div>
            </div>
            <span>COPYRIGHT 2023. ALL RIGHTS RESERVED.</span>
          </div>
        </footer>
      </section>
      <div class="bottomDiv"></div>
    </div>
    <footer>
      <div class="content">
        <div class="logo">
          <span>
            <img src="@/assets/img/Logo.png" alt="" />
          </span>
          <div class="name">
            <span>LOSANGELES</span>
            <span>MOUNTAINS</span>
          </div>
        </div>
        <span>COPYRIGHT 2023. ALL RIGHTS RESERVED.</span>
      </div>
    </footer>
  </div>
  <div class="preload">
    <img src="@/assets/img/slider2.png" alt="" />
  </div>
</template>

<script>
import $ from "jquery";
export default {
  name: "mainComponent",
  props: {
    msg: String,
  },
  data() {
    return {
      loader: true,
      tabSelected: "",
      n: 1,
      counter: 0,
      interval: null,
      tempInterval: null,
      mountain: "mountain1",
      navHeight: 52,
      selectedNav: "history",
    };
  },
  methods: {
    onWindowLoad() {
      this.loader = false;
    },
    slider() {
      let self = this;
      $(".mainImage div").removeClass("selected");
      $(".controls .control").removeClass("selected");
      setTimeout(function () {
        $(".mainImage div:nth-child(" + self.n + ")").addClass("selected");
        $(".controls .control:nth-child(" + self.n + ")").addClass("selected");
      }, 400);
    },
    sliderControl(n) {
      let self = this;
      self.n = n;
      self.slider();
      clearInterval(self.interval);
      clearInterval(self.tempInterval);
      self.counter = 0;
      self.tempInterval = setInterval(function () {
        self.counter = self.counter + 10;
        if (self.counter == 3000) {
          clearInterval(self.tempInterval);
          self.counter == 0;
          self.interval = setInterval(self.newInterval, 4000);
        }
      }, 10);
    },
    newInterval() {
      let self = this;
      if (self.n < 4) {
        self.n++;
        self.slider();
      } else {
        self.slider();
        self.n = 1;
      }
    },
    scroll() {
      const self = this;
      this.tabSelected = "";
      const hero = document.getElementById("hero");
      this.$smoothScroll({
        scrollTo: hero,
        duration: 2000,
        offset: self.navHeight * -1,
        updateHistory: false,
      });
    },
    mobNav(name) {
      let selectedNav = this.selectedNav;
      let button = document.getElementById("button");
      this.$smoothScroll({
        scrollTo: button,
        duration: 1000,
        offset: window.innerHeight,
        updateHistory: false,
      });
      if (selectedNav == name) {
        //do nothing
      } else {
        $(".navigations a").removeClass("selected");
        $("." + selectedNav).slideUp();
        setTimeout(function () {
          $(".link" + name).addClass("selected");
          $("." + name).slideDown(500);
        }, 500);
        this.selectedNav = name;
      }
    },
  },
  mounted() {
    let self = this;
    window.addEventListener("load", self.onWindowLoad);
    self.navHeight = 52;
    $(document).ready(function () {
      let R = 255;
      let G = 255;
      let B = 255;
      let height = window.innerHeight;
      let mobileHeight = $(window).height();
      let mobileTabHeight = $(window).height() - 179;
      let width = window.innerWidth;
      let margin;
      let shadow1 = 0;
      $("html").css({
        "--border-color": "rgb(" + R + "," + G + "," + B + ")",
        "--mobileHeight": mobileHeight + "px",
        "--mobileTabHeight": mobileTabHeight + "px",
      });

      if (width > 768) {
        margin = height * 2 - self.navHeight + "px";
        $("html").css({
          "--border-color": "rgb(" + R + "," + G + "," + B + ")",
          "--height": height - self.navHeight + "px",
          "--margin": margin,
        });
        var cnt = $(".mobDiv").contents();
        $(".mobDiv").replaceWith(cnt);
      } else {
        margin = "0px";
        $(".mobDiv").addClass("tabs");
        $("#history").removeAttr("id");
        $(".history").attr("id", "history");
        $(".team").slideUp("fast");
        $(".history").slideDown("fast");
        $(".linkhistory").addClass("selected");
      }

      $(window).scroll(function () {
        /* Common jQuery */
        $(".hero").css("opacity", 1 - $(window).scrollTop() / height);
        $("nav").css(
          "background-color",
          "rgba(255,255,255," +
            (-1 + $(window).scrollTop() / (height / 2)) +
            ")"
        );
        $("nav .name").css(
          "opacity",
          -1 + $(window).scrollTop() / (height / 2)
        );
        if ($(window).scrollTop() <= height) {
          shadow1 = $(window).scrollTop() * (2 / height);
        }
        $("nav").css(
          "box-shadow",
          "0 " + shadow1 + "px " + shadow1 + "px 0 rgba(0,0,0,0.3)"
        );

        /* jQuery for Desktop */
        if (width > 768) {
          if ($(window).scrollTop() <= height) {
            R = 255 - $(window).scrollTop() * (190 / height);
            G = 255 - $(window).scrollTop() * (176 / height);
            B = 255 - $(window).scrollTop() * (148 / height);
            shadow1 = $(window).scrollTop() * (2 / height);
          }
          $("html").css({
            "--border-color": "rgb(" + R + "," + G + "," + B + ")",
          });
          if ($(window).scrollTop() < height - self.navHeight) {
            $(".history").css({ position: "relative", "margin-top": "100vh" });
          } else {
            $(".history").css({
              position: "fixed",
              "margin-top": self.navHeight + "px",
            });
            $(".history").css(
              "opacity",
              1 - ($(window).scrollTop() - height) / height
            );
          }
        } else {
          /* jQuery for Mobile/tablet */
          if ($(window).scrollTop() < mobileHeight - self.navHeight) {
            $(".button").css({ position: "static", marginTop: mobileHeight });
            $(".tabs").css("margin-top", "0");
          } else {
            $(".button").css({
              position: "fixed",
              marginTop: 0,
            });
            $(".tabs").css("margin-top", parseInt(mobileHeight + 51) + "px");
          }
        }
      });
      self.interval = setInterval(self.newInterval, 4000);
    });
  },
  created() {
    console.log("hello");
  },
  beforeUnmount() {
    clearInterval(this.interval);
    window.removeEventListener("load", this.onWindowLoad);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
html {
  --border-color: 0;
  --height: 0;
  --mobileHeight: 0;
  --mobileTabHeight: 0;
  --margin: 0;
}
.loaderContainer {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
  background-color: #fff;
  width: 100%;
  height: 100vh;
  .loaderMain {
    position: absolute;
    text-align: center;
    font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS",
      sans-serif;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    h5 {
      margin: 5px 0px;
      font-weight: normal;
    }
    .loader {
      margin: auto;
      display: grid;
      grid-template-columns: 33% 33% 33%;
      grid-gap: 0px;
      width: 100px;
      height: 100px;

      > div {
        position: relative;
        width: 100%;
        height: 100%;
        background: #414f6b;
        transform: scale(0);
        transform-origin: center center;
        animation: loader 1s infinite linear;

        &:nth-of-type(7) {
        }

        &:nth-of-type(1),
        &:nth-of-type(5),
        &:nth-of-type(9) {
          animation-delay: 0.2s;
        }

        &:nth-of-type(4),
        &:nth-of-type(8) {
          animation-delay: 0.1s;
        }

        &:nth-of-type(2),
        &:nth-of-type(6) {
          animation-delay: 0.3s;
        }

        &:nth-of-type(3) {
          animation-delay: 0.4s;
        }
      }
    }

    @keyframes loader {
      0% {
        transform: scale(0);
      }
      40% {
        transform: scale(1);
      }
      80% {
        transform: scale(1);
      }
      100% {
        transform: scale(0);
      }
    }
  }
}
.mountain1-enter-active,
.mountain1-leave-active {
  transition: all 0.5s;
}

.mountain1-enter-from,
.mountain1-leave-to {
  transform: translateX(-100%);
}
.mountain2-enter-active,
.mountain2-leave-active {
  transition: all 0.5s;
}

.mountain2-enter-from,
.mountain2-leave-to {
  transform: translateX(100%);
}
.container {
  font-family: bahnschrift;
  max-width: 100%;
  overflow-x: hidden;
  @media only screen and (max-width: 768px) {
    position: relative;
  }
  .content {
    width: 70%;
    margin: auto;
    @media only screen and (max-width: 1000px) {
      width: 90%;
    }
  }
  nav {
    background-color: rgba(255, 255, 255, 0);
    position: fixed;
    z-index: 99;
    top: 0;
    width: 100%;
    padding: 10px 0px;
    box-sizing: border-box;
    .content {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .navigations {
      @media only screen and (max-width: 768px) {
        display: none;
      }
    }
  }
  .logo {
    display: flex;
    align-items: center;
    cursor: pointer;
    img {
      width: 32px;
      height: 32px;
      opacity: 1;
      margin-right: 10px;
    }
    .name {
      font-weight: bold;
      opacity: 0;
      span {
        display: block;
        font-size: 16px;
        line-height: 14px;
        &:first-of-type {
          color: #4d4d4d;
        }
        &:last-of-type {
          color: #414f6b;
        }
      }
    }
  }
  .navigations {
    a {
      position: relative;
      padding: 7px 15px;
      border-bottom: 2px solid var(--border-color);
      text-decoration: none;
      color: var(--border-color);
      font-weight: normal;
      transition-duration: 0.3s;
      @media only screen and (max-width: 768px) {
        font-size: 14px;
      }
      &.selected {
        &::after {
          border-color: var(--border-color);
          transition: height 0.25s ease-out 0.5s;
          width: 100%;
          height: 100%;
        }
        &::before {
          border-color: var(--border-color);
          transition: height 0.25s ease-out, width 0.25s ease-out 0.25s;
          width: calc(100% - 2px);
          height: 100%;
        }
      }
      &:first-of-type {
        margin-right: 50px;
      }
      &::before,
      &::after {
        content: "";
        position: absolute;
      }
      &::before {
        border-left: 2px solid transparent;
        border-top: 2px solid transparent;
        height: 0;
        width: 0;
        bottom: 0;
        left: 0;
      }
      &:hover::before {
        border-color: var(--border-color);
        transition: height 0.25s ease-out, width 0.25s ease-out 0.25s;
        width: calc(100% - 2px);
        height: 100%;
      }

      &::after {
        top: 0;
        right: 0;
        border-right: 2px solid transparent;
        height: 0;
        width: 100%;
      }
      &:hover::after {
        border-color: var(--border-color);
        transition: height 0.25s ease-out 0.5s;
        height: 100%;
      }
    }
  }
  #hero {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
  }
  .hero {
    position: fixed;
    top: 0;
    z-index: -1;
    background-image: url("@/assets/img/hero.png");
    background-size: cover;
    background-position: center;
    width: 100%;
    height: 100vh;
    overflow: hidden;
    @media only screen and (max-width: 768px) {
      background-position-x: 45%;
      height: var(--mobileHeight);
    }
    img {
      width: 100%;
      height: 100%;
      opacity: 0.3;
    }
  }
  #history {
    position: absolute;
    top: 100vh;
    left: 0;
    width: 100%;
    height: var(--height);
    @media only screen and (max-width: 768px) {
      position: static;
      width: auto;
      height: auto;
      overflow-y: hidden;
    }
  }
  .button {
    padding: 10px 0;
    margin-top: 100vh;
    box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.3);
    background-color: #414f6b;
    display: none;
    z-index: 99;
    width: 100%;
    top: 52px;
    @media only screen and (max-width: 768px) {
      display: block;
    }
    &:last-of-type {
      margin-top: 0;
    }
    .navigations {
      @media only screen and (max-width: 768px) {
        display: flex;
        justify-content: center;
      }
      a {
        z-index: 2;
        color: #fff;
        border-color: #fff;
        &.selected:hover::before,
        &.selected:hover::after {
          width: calc(100% - 2px);
          height: 100%;
        }
        &:hover::before,
        &:hover::after {
          width: 0;
          height: 0;
        }
      }
    }
  }
  .tabs {
    height: var(--mobileTabHeight);
    background-color: #fff;
    width: 100%;
    overflow-y: scroll;
    z-index: 5;
    .bottomDiv {
      display: none;
      @media only screen and (max-width: 768px) {
        display: block;
        width: 100%;
        height: 10px;
        background-color: #414f6b;
      }
    }
  }
  .history {
    margin-top: 100vh;
    position: relative;
    z-index: 1;
    top: 0;
    width: 100%;
    background-color: #fff;
    @media only screen and (max-width: 768px) {
      margin-top: 0;
      margin-bottom: 50px;
    }
    .mainImage {
      height: var(--height);
      overflow: hidden;
      @media only screen and (max-width: 768px) {
        height: 400px;
        position: relative;
      }
      .img {
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;
        opacity: 0;
        transform-origin: left center;
        transition-duration: 0.5s;
        background-position: center;
        background-size: cover;
        &.selected {
          opacity: 1;
        }
      }
    }
    .controls {
      width: 100%;
      height: 200px;
      background-color: rgba(65, 79, 107, 0.7);
      position: absolute;
      bottom: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      @media only screen and (max-width: 1000px) {
        height: 150px;
      }
      @media only screen and (max-width: 768px) {
        height: 30px;
        position: static;
        background-color: #fff;
      }
      .control {
        position: relative;
        max-width: 200px;
        max-height: 106px;
        margin-left: 20px;
        height: fit-content;
        cursor: pointer;
        @media only screen and (max-width: 1000px) {
          max-width: 150px;
          max-height: 79px;
        }
        @media only screen and (max-width: 768px) {
          background-color: #63769d;
          height: 10px;
          width: 10px;
          border-radius: 10px;
        }
        img {
          max-width: 100%;
          height: 100%;
          @media only screen and (max-width: 768px) {
            display: none;
          }
        }
        &:first-of-type {
          margin-left: 0;
        }
        &::after {
          content: "";
          width: 100%;
          height: 100%;
          background-color: #000;
          opacity: 0.5;
          position: absolute;
          top: 0;
          left: 0;
          transition-duration: 0.5s;
          @media only screen and (max-width: 768px) {
            opacity: 1;
            border-radius: 10px;
          }
        }
        &:hover {
          &::after {
            opacity: 0;
          }
        }
        &.selected {
          &::after {
            opacity: 0;
          }
        }
      }
    }
    .mainContent {
      @media only screen and (max-width: 768px) {
        position: static;
      }
    }
  }
  .mainContent {
    position: absolute;
    width: 100%;
    top: 0;
    @media only screen and (max-width: 768px) {
      position: static;
    }
    .content {
      .number {
        display: flex;
        align-items: end;
        h1 {
          margin: 0;
          font-size: 200px;
          line-height: 190px;
          opacity: 0.7;
          color: #414f6b;
          @media only screen and (max-width: 1920px) {
            font-size: 150px;
            line-height: 140px;
          }
          @media only screen and (max-width: 1440px) {
            font-size: 100px;
            line-height: 90px;
          }
          @media only screen and (max-width: 768px) {
            font-size: 60px;
            line-height: 50px;
          }
        }
        div {
          h2 {
            color: #414f6b;
            transform: translateY(120px);
            font-size: 60px;
            margin: 0;
            @media only screen and (max-width: 1920px) {
              font-size: 40px;
              transform: translateY(90px);
            }
            @media only screen and (max-width: 1440px) {
              font-size: 30px;
              transform: translateY(60px);
            }
            @media only screen and (max-width: 768px) {
              font-size: 20px;
              line-height: 15px;
              transform: translateY(30px);
            }
          }
        }
      }
      p {
        color: #414f6b;
        margin: 0;
        margin-top: 0px;
        margin-left: 55px;
        font-size: 30px;
        @media only screen and (max-width: 1920px) {
          font-size: 22px;
        }
        @media only screen and (max-width: 1440px) {
          font-size: 18px;
        }
        @media only screen and (max-width: 768px) {
          margin-left: 10px;
          margin-top: 10px;
          font-size: 14px;
        }
      }
    }
  }
  .team {
    position: absolute;
    margin-top: var(--margin);
    width: 100%;
    z-index: 2;
    background-color: #fff;
    height: var(--height);
    @media only screen and (max-width: 768px) {
      height: auto;
      position: relative;
      margin-top: 0;
      z-index: 3;
    }
    .content {
      display: flex;
      align-items: center;
      @media only screen and (max-width: 768px) {
        display: block;
      }
      .number {
        margin-left: 25px;
        @media only screen and (max-width: 768px) {
          margin-left: 0px;
        }
      }
      p {
        margin-left: 30px;
        @media only screen and (max-width: 768px) {
          margin-left: 10px;
        }
      }
    }
    .teamNav {
      margin-top: 270px;
      background-color: #414f6b;
      box-sizing: border-box;
      @media only screen and (max-width: 1920px) {
        margin-top: 200px;
      }
      @media only screen and (max-width: 1440px) {
        margin-top: 150px;
      }
      @media only screen and (max-width: 768px) {
        background-color: #fff;
        margin-top: 30px;
      }
      .content {
        @media only screen and (max-width: 768px) {
          display: flex;
          justify-content: center;
        }
      }
      span {
        padding: 10px 25px;
        font-size: 22px;
        letter-spacing: -0.3px;
        display: inline-block;
        color: #a6b1c7;
        cursor: pointer;
        transition-duration: 0.3s;
        @media only screen and (max-width: 768px) {
          padding: 8px 20px;
          font-size: 18px;
        }
        &:last-of-type {
          margin-left: 10px;
        }
        &:hover {
          color: #414f6b;
          background-color: #a6b1c7;
          text-decoration: underline;
        }
        &.selected {
          color: #414f6b;
          background-color: #a6b1c7;
          text-decoration: underline;
        }
      }
    }
    .slider {
      width: 100%;
      height: 60%;
      overflow: hidden;
      margin-bottom: 50px;
      @media only screen and (max-width: 768px) {
        height: 400px;
      }
      .mountain1 {
        background-image: url("@/assets/img/slider1.png");
        height: 100%;
        width: 100%;
      }
      .mountain2 {
        background-image: url("@/assets/img/slider2.png");
        height: 100%;
        width: 100%;
      }
      & > div {
        background-size: cover;
      }
      .content {
        position: relative;
        .table {
          z-index: 3;
          position: absolute;
          top: 50px;
          left: 20px;
          background-color: rgba(255, 255, 255, 0.5);
          padding: 20px;
          box-sizing: border-box;
          display: flex;
          flex-direction: column;
          align-items: start;
          @media only screen and (max-width: 768px) {
            left: 0;
          }
          h4 {
            font-weight: bold;
            color: #414f6b;
            font-size: 30px;
            display: block;
            margin: 0;
            @media only screen and (max-width: 768px) {
              font-size: 25px;
            }
          }
          ul {
            list-style-type: none;
            padding: 0;
            color: #414f6b;
            font-weight: lighter;
            li {
              margin-bottom: 10px;
              transition-duration: 0.3s;
              cursor: pointer;
              @media only screen and (max-width: 768px) {
                font-size: 14px;
              }
              &:hover {
                padding: 10px 0;
              }
              .name {
                margin-left: 40px;
              }
            }
          }
        }
      }
    }
    footer {
      display: block;
      position: absolute;
      bottom: 0;
      @media only screen and (max-width: 768px) {
        display: none;
      }
    }
  }
  footer {
    background-color: #414f6b;
    color: #63769d;
    width: 100%;
    display: none;
    @media only screen and (max-width: 768px) {
      display: block;
      position: static;
    }
    .content {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 0px;
      @media only screen and (max-width: 768px) {
        flex-direction: column;
      }
      .logo {
        & > span {
          display: flex;
          align-items: center;
          position: relative;
          margin-top: 0;
          &::after {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            opacity: 0.7;
            width: 32px;
            height: 100%;
            background-color: #414f6b;
          }
        }
        .name {
          opacity: 1;
          span {
            margin-top: 0;
            color: #63769d;
            font-style: normal;
            font-size: 16px;
          }
        }
      }
      span {
        font-style: italic;
        font-size: 14px;
        @media only screen and (max-width: 768px) {
          font-size: 12px;
          margin-top: 10px;
        }
      }
    }
  }
}
.preload {
  display: none;
}
</style>
