
<template>
  <ScaleBox :width="1920" :height="1080" bgc="transparent" :delay="100">
  <div class="pabout">
    <div class="ptitle">PRODUCTS</div>
    <div class="ptheme">
      <div class="exp">Service we offer</div>
      <div class="titleLeft" style="width: 20%; float:left;">
        <p @click="clickOverview(0)"><a>1.Overview</a></p>
        <p @click="clickOverview(1)"><a>2.Taxonomy Tree</a></p>
        <p @click="clickOverview(2)"><a>3.Alpha diversity</a></p>
        <p @click="clickOverview(2)"><a>4.Beta diversity</a></p>
        <p @click="clickOverview(3)"><a>5.Dimension reduction</a></p>
        <p @click="clickOverview(4)"><a>6.Enterotype</a></p>
        <p @click="clickOverview(5)"><a>7.Differential testing</a></p>
        <p @click="clickOverview(6)"><a>8.Classifier</a></p>
        <p @click="clickOverview(6)"><a>9.FMT overview</a></p>
        <p @click="clickOverview(7)"><a>10.Rarefraction curve</a></p>
        <p @click="clickOverview(7)"><a>11.Correlation Network</a></p>
        <p @click="clickOverview(8)"><a>12.Our dataset</a></p>
      </div>
      <!-- <div class="titleLeft" style="width: 20%; float:left;">
        <p @click="clickOverview(0)"><a>1.Overview</a></p>
        <p @click="clickOverview(1)"><a>2.Taxonomy Tree</a></p>
        <p @click="clickOverview(2)"><a>3.Alpha diversity</a></p>
        <p @click="clickOverview(3)"><a>4.Beta diversity</a></p>
        <p @click="clickOverview(4)"><a>5.Dimension reduction</a></p>
        <p @click="clickOverview(5)"><a>6.Enterotype</a></p>
        <p @click="clickOverview(6)"><a>7.Differential testing</a></p>
        <p @click="clickOverview(7)"><a>8.Classifier</a></p>
        <p @click="clickOverview(8)"><a>9.FMT overview</a></p>
        <p @click="clickOverview(9)"><a>10.Rarefraction curve</a></p>
        <p @click="clickOverview(10)"><a>11.Correlation Network</a></p>
        <p @click="clickOverview(11)"><a>12.Our dataset</a></p>
      </div> -->
      <el-carousel arrow="always" ref="test" trigger="click" autoplay="false" style="width: 60%;float: left;">
        <el-carousel-item v-for="item in pageUrlArr" :key="item">
          <div class="right-con" :style="{backgroundImage: 'url(' + item.imgUrl + ')', backgroundSize:'100%'}">
          <!-- <div class="right-con"> -->
            <!-- <img src: item.imgUrl alt=""> -->
          <!-- <div class="biaoti">{{ item.title }}</div>
          <div style="float: left; width:30%;height:100%;margin-left: 150px; margin-top: 10px;">
            <div class="content">{{ item.content }}</div>
          </div>
          <div style="float:right ; width:40%;margin-right: 150px;" class="pimg">
            <img :src="item.imgUrl" />
          </div> -->
        </div>
        </el-carousel-item>
      </el-carousel>
    </div>
  </div>
</ScaleBox>
</template>
<script>
export default {
  data() {
    return {
  //     pageUrlArr: [{
  //       imgUrl: '/src/assets/pr/pr1.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr2.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr3.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr3.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr4.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr5.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr6.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr7.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr7.png',
  //     }, {
  //       imgUrl: '/src/assets/pr/pr8.png'
  //     }, {
  //       imgUrl: '/src/assets/pr/pr8.png',
  //     }, {
  //       imgUrl: '/src/assets/pr/pr9.png',
  //     }
  //     ]
  //   }
  // },
  pageUrlArr: [{
        imgUrl: new URL('../assets/pr/pr1.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr2.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr3.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr4.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr5.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr6.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr7.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr8.png', import.meta.url)
      }, {
        imgUrl: new URL('../assets/pr/pr9.png', import.meta.url)
      }
      ]
    }
  },
  methods: {
    clickOverview(val) {
      this.$refs.test.setActiveItem(val)

    }
  }
}


</script>
<style>
.pabout {
  width: 100%;
  min-height: 850px;
  display: block;
  align-items: center;
  background-color: rgb(249, 251, 253);
}
.el-carousel__item{
  height: 500px;
}
.el-carousel__arrow .el-carousel__arrow--left{
  background-image: url(@/assets/lbl.png);
}

.ptitle {
  width: 150px;
  height: 40px;
  display: inline-block;
  margin-left: 250px;
  margin-top: 20px;
  font-family: Lao UI;
  font-size: 24px;
  text-align: center;
  color: aliceblue;
  border-radius: 10px;
  background-color: #29aae3;
  font-weight: bolder;
  text-decoration: underline
}

.ptheme {
  min-width: 1500px;
}
.exp {
  text-align: left;
  min-width: 1600px;
  height: 50px;
  font-family: Lato Black;
  font-size: 36px;
  margin-left: 250px;
  font-weight: bolder;

}

.titleLeft {
  margin-top: 35px;
  margin-left: 250px;
}
.titleLeft p{
  font-family: Arial;
  font-size: 18px;
  margin-top: 10px;
  color: cornflowerblue;
}

.titleLeft p a {
  display: inline-block;
  font-weight: bolder;
  color: rgb(32, 56, 100);

}
.el-carousel__container{
  height: 600px;
  margin-right: 0px;
}
.el-carousel--horizontal{
  height: 600px;
}
.right-con{
  height: 600px;
}
/* .biaoti {
  margin-top: 20px;
  width: 1600px;
  height: 40px;
  display: inline-block;
  font-family: Arial;
  font-size: 24px;
  color: cornflowerblue;
  color: aliceblue; 
  border-radius: 10px;
  font-weight: bolder;
  margin-left: 150px;
}
.pimg{
  width: 466px;
  height: 333;
}  */ 

</style>
