<!-- rotation -->
<template>
   <div class="outer">

        <div class="main">
            <div class="out" :class="classRotate">
                <div class="left">
                    <a href="">
                        <img src="../assets/image/1.jpg" alt="">
                    </a>
                    <a href="">
                        <img src="../assets/image/2.jpg" alt="">
                    </a>
                </div>
                <div class="right">
                    <a href="">
                        <img src="../assets/image/3.jpg" alt="">
                    </a>
                    <a href="">
                        <img src="../assets/image/4.jpg" alt="">
                    </a>
                </div>
                <div class="pre">
                    <a href="">
                        <img src="../assets/image/5.jpg" alt="">
                    </a>
                    <a href="">
                        <img src="../assets/image/6.jpg" alt="">
                    </a>
                </div>
                <div class="back">
                    <a href="">
                        <img src="../assets/image/7.jpg" alt="">
                    </a>
                    <a href="">
                        <img src="../assets/image/8.jpg" alt="">
                    </a>
                </div>
              </div>
              <div class="tips" @click="switchImage($event)" @mouseover.stop="switchImage($event)">
                  <!-- <span v-for="(val) in tipsArry" :key="val" :id="val" :class="[tip,'tip']" ></span> -->
                  <span id="1" :class="[activeTip==1?'tiphover':'','tip']" ></span>
                  <span id="2" :class="[activeTip==2?'tiphover':'','tip']" ></span>
                  <span id="3" :class="[activeTip==3?'tiphover':'','tip']" ></span>
                  <span id="4" :class="[activeTip==4?'tiphover':'','tip']" ></span>
                  
              </div>
        </div>
        <div class="prev">
            <div class="icon-pre" @click="carouselPre()"></div>
        </div>
        <div class="next">
            <div class="icon-next" @click="carouselNext()"></div>
        </div>
    </div>
</template>

<script>
export default {
  props: {},
  data() {
    return {
      activeTip: 1,
      timer: null,
      operateIntervaTime: "intime" //'outtime'
    };
  },

  components: {},

  computed: {
    classRotate() {
      return this.activeTip === 1
        ? "totate_one"
        : this.activeTip === 2
          ? "totate_two"
          : this.activeTip === 3 ? "totate_three" : "totate_four";
    }
  },

  methods: {
    switchImage(e) {
      let setTip = e.target.id ? Number(e.target.id) : this.activeTip;
      this.activeTip = setTip;
    },
    startCarousel() {
      //   let _that=this;
      //   this.timer=setInterval(function(){
      //       _that.activeTip=_that.activeTip<4&&_that.activeTip>=1?_that.activeTip+1:1;
      //   },3000);
      this.timer = setInterval(() => {
        this.activeTip =
          this.activeTip < 4 && this.activeTip >= 1 ? this.activeTip + 1 : 1;
      }, 4000);
    },
    clearCarousel() {
      clearInterval(this.timer);
      this.timer = null;
      this.operateIntervaTime = "intime";
    },
    carouselPre() {
      this.clearCarousel();
      this.activeTip =
        this.activeTip <= 4 && this.activeTip > 1 ? this.activeTip - 1 : 4;
      setTimeout(() => {
        this.operateIntervaTime = "outtime";
      }, 5000);
    },
    carouselNext() {
      this.clearCarousel();
      this.activeTip =
        this.activeTip < 4 && this.activeTip >= 1 ? this.activeTip + 1 : 1;
      setTimeout(() => {
        this.operateIntervaTime = "outtime";
      }, 5000);
    }
  },
  watch: {
    operateIntervaTime() {
      if (this.timer === null && this.operateIntervaTime === "outtime") {
        this.startCarousel();
      }
    }
  },
  mounted() {
    this.startCarousel();
  }
};
</script>
<style lang='scss' scoped>
.tips {
  width: 250px;
  height: 10px;
  white-space: nowrap;
  position: absolute;
  background-color: rgba(255, 255, 255, 0);
  left: 50%;
  top: 200px;
  margin-left: -125px;
  line-height: 10px;
  .tip {
    cursor: pointer;
    display: inline-block;
    width: 50px;
    height: 8px;
    border-radius: 4px;
    margin: 0 2px;
    background-color: rgba(255, 255, 255, 0.5);
  }
  .tiphover {
    background-color: rgba(255, 255, 255, 0.9);
  }
  .tip:hover {
    background-color: rgba(255, 255, 255, 0.9);
  }
}
.outer {
  min-width: 1070px;
  padding: 0 100px;
  height: 220px;
}
.outer > div {
  float: left;
  height: 220px;
}
.prev > div,
.next > div {
  background-image: url("../assets/image/icon_sprite.png");
  display: inline-block;
  width: 20px;
  height: 40px;
  cursor: pointer;
}
.prev {
  margin-left: -100%;
  background-color: rgba(200, 200, 200, 0.3);
  width: 100px;
  position: relative;
  left: -100px;
  line-height: 220px;
  .icon-pre {
    background-position: -20px -120px;
  }
}
.next {
  position: relative;
  float: right;
  margin-right: -100%;
  background-color: rgba(200, 200, 200, 0.3);
  width: 100px;
  line-height: 220px;
  .icon-next {
    background-position: 0 -120px;
  }
}
.main {
  width: 100%;
  overflow: hidden;
  position: relative;
}
.out {
  width: 1060px;
  height: 220px;
  position: relative;
  transform-style: preserve-3d;
  margin: 0px auto;
  transition: all 1s linear;
  // animation:rotate 18s linear infinite;
  /*transform: rotateX(20deg) rotateY(120deg);*/
  transform-origin: 50% 50% -530px;
}
.totate_one {
  transform: rotateY(0deg);
}
.totate_two {
  transform: rotateY(-90deg);
}
.totate_three {
  transform: rotateY(-180deg);
}
.totate_four {
  transform: rotateY(-270deg);
}
.out > div {
  width: 100%;
  height: 100%;
  position: absolute;
  font-size: 60px;
  text-align: center;
  line-height: 220px;
  color: #daa520;
  white-space: nowrap;
}
.out > div a {
  display: inline-block;
  width: 525px;
  height: 100%;
}
.out > div img {
  width: 100%;
  height: 100%;
}
.left {
  background-color: rgba(255, 255, 0, 0.1);
  transform-origin: left;
  transform: rotateY(90deg);
}
.right {
  background-color: rgba(0, 0, 255, 0.1);
  transform-origin: right;
  transform: rotateY(-90deg);
}
.pre {
  background-color: rgba(0, 255, 255, 0.1);
  transform: translateZ(-1160px);
}
.back {
  background-color: rgba(99, 66, 33, 0.1);
}
//  @Keyframes rotate{
//   0%{
//         -webkit-transform:rotateX(0deg) rotateY(0deg);
//   }
//   100%{
//         -webkit-transform:rotateX(0deg) rotateY(360deg) ;
//   }
//   }
</style>