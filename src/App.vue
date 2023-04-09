<script>
import ProductsView from "./views/ProductsView.vue";
import ExplainView from "./views/ExplainView.vue";
import ReviewsView from "./views/ReviewsView.vue";
import TeamView from "./views/TeamView.vue";
import PublicationsView from "./views/PublicationsView.vue";
import HomeView from "./views/HomeView.vue";
export default {
   components: {
      ProductsView,
      ExplainView,
      ReviewsView,
      TeamView,
      PublicationsView,
      HomeView,
   },
   data() {
      return {
           posOpt:[
                    {name:"index",code:0,icon:"el-icon-pie-chart"},
                    {name:"PRODUCTS",code:1,icon:"el-icon-pie-chart"},
                    {name:"HOW",code:2,icon:"el-icon-pie-chart"},
                    {name:"REVIEWS",code:3,icon:"el-icon-pie-chart"},
                    {name:"TEAM",code:4,icon:"el-icon-pie-chart"},
                    {name:"PUBLICATIONS",code:5,icon:"el-icon-pie-chart"},
            ],
       }
   },
   methods: {
          //Tba点击
          tabClick(code){
               //判断code 状态 ，如果等于0，点击后就滑动到id为(#floor0)的锚点内容区域，也就是根据code状态码 展示对应的锚点
                if(code ==0){
                    this.goAnchor('floor0');
                    // this.goAnchor(this.$refs.floor0);
                }else if (code ==1) {
                    this.goAnchor('floor1');
                    // this.goAnchor(this.$refs.floor1);
                }
                else if (code ==2) {
                    this.goAnchor('floor2');
                    // this.goAnchor(this.$refs.floor2);
                }
                else if (code ==3) {
                    this.goAnchor('floor3');
                    // this.goAnchor(this.$refs.floor3);
                }
                else if (code ==4) {
                    this.goAnchor('floor4');
                    // this.goAnchor(this.$refs.floor4);
                }
                else{
                    this.goAnchor('floor5');
                    // this.goAnchor(this.$refs.floor5);
                }
            },
            //锚点跳转
            goAnchor(selector) {
                // var anchor = this.$el.querySelector(selector);//获取元素
                var anchor = document.getElementById(selector);//获取元素
                console.log(anchor)
                let total;
                let disFixed =document.getElementsByClassName("vux-fixed")[0];
                if(disFixed){
                    total = anchor.offsetTop;
                }else{
                    total = anchor.offsetTop;
                }
                let distance = document.documentElement.scrollTop || document.body.scrollTop;
                // 计算每一小段的距离
                let step = total/6;
                (function smoothDown () {
                    if (distance < total) {
                        distance += step;
                        // 移动一小段
                        document.body.scrollTop = distance;
                        document.documentElement.scrollTop = distance;
                        // 设定每一次跳动的时间间隔为10ms
                        setTimeout(smoothDown, 10)
                    } else {
                        // 限制滚动停止时的距离
                        document.body.scrollTop = total;
                        document.documentElement.scrollTop = total
                    }
                })()

            },
   }
}
</script>

<template>
  <div class="wrapper" style="background-color:rgb(255, 255, 255); position: sticky;top:0; z-index: 999;   width: 100%;">
      <nav>
        <div class="flool1" @click="tabClick(0)" ><img alt="Vue logo" class="logo" src="@/assets/log.svg"></div>
        <div class="flool2" @click="tabClick(1)" ><a style="color: rgb(128, 128, 128); cursor:pointer">PRODUCTS</a></div>
        <div class="flool2" @click="tabClick(2)" ><a style="color: rgb(128, 128, 128); cursor:pointer">HOW DOES IT WORK</a></div>
        <div class="flool2" @click="tabClick(3)"><a style="color: rgb(128, 128, 128); cursor:pointer">REVIEWS</a></div>
        <div class="flool2" @click="tabClick(4)"><a style="color: rgb(128, 128, 128); cursor:pointer">TEAM</a></div>
        <div class="flool2" @click="tabClick(5)"><a style="color: rgb(128, 128, 128); cursor:pointer">PUBLICATIONS</a></div> 
        <button type="button" src="@/assets/title.png" >ORDER　NOW</button>
      </nav>
    </div>
	<div>
		<HomeView ref="floor0" id="floor0"></HomeView>
		<ProductsView id="floor1" ref="floor0"  ></ProductsView>
		<ExplainView id="floor2" ref="floor0" ></ExplainView>
		<ReviewsView id="floor3" ref="floor0" ></ReviewsView>
		<TeamView id="floor4" ref="floor0" ></TeamView>
		<PublicationsView id="floor5" ref="floor0" ></PublicationsView>
	</div>
  <div class="appbottom">
  <div class="appbottom_info">
    <ul>
    <li>Contact information：56495443213211     <a>12464646@favxzvz.com</a></li>
    <li>Address :  amojckljvkljl;kasjdkzxmc.zxvljkl;xjbklxn m,.n,.n;zln</li>
    <li>Hope to receiving your invitation to cooperate.</li>
    </ul>
  </div>
  </div>
</template>

<style lang="less" scoped>
.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  height: 70px;
}

.appbottom{
  display: block;
  width: 100%;
  height: 10%;
  background: url(@/assets/background_bottom.png) no-repeat  ;
  position: relative;
  background-size:100%;
  float: left;
}
.appbottom_info {
  margin-left: 35%;
  padding-top: 50px;
}
.appbottom_info ul {
}
.appbottom_info ul li {
  font-size: 20px;
  color:azure;
}
.appbottom_info ul li a {
  color:azure;
  text-decoration: underline
}
nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}
.flool1
{
  width: 10%;
  float: left;
  margin-top: 20px;
  margin-left: 10px;
  margin-right: 400px;
}
.flool1 img{
  width: 127px;
}
.flool2{
  margin-left: 40px;
  margin-top: 20px;
  float: left;
  font-family: 思源黑体 CN Normal;
  font-size: 15px;
}
.flool2 a{
  font-family: 思源黑体 CN Normal;
  font-size: 15px;
  display: inline-block;
}

nav button{
  margin-top: 10px;
  font-family: Lao UI;
  font-size: 15px;
  text-align: center;
  color: rgb(255, 255, 255);
  border-radius: 10px;
  background-color: rgb(41, 170, 227);
  font-weight: bolder;
  background-image: url(./assets/title.png);
  background-size: contain;
  /* background-color: rgb(0, 201, 201); */
  margin-left: 25%;
  width: 150px;
  height: 37px;
  /* border-radius: 10px; */
  border: 0;
}

nav a:first-of-type {
  border: 0;
}

  header {
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: block;
    place-items: flex-start;
    flex-wrap: wrap;
  }
</style>
