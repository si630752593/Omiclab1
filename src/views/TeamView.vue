<script setup lang="ts">
</script>
<template>
  <ScaleBox :width="1920" :height="1080" bgc="transparent" :delay="100">
  <div class="tabout">
    <div class="ttitle">SUSTENTATION</div>
    <div class="ttheme">Team</div>
     <div class="tinfo">
     <div class="user1">
     <div class="userp1"> <img src="@/assets/team1.png" alt=""></div>
     <div class="userinfo1"><p>英国历史学家彼德·伯克在《图像证史》一书中力图说明的基本论点是:图像如同文本和口述证词一样,也是历史证据的一种重要形式．"左图右书"也是我国古代治史传统．近年来,画作、地图、历史事件及实物的照片等可视材料在史学研究、历史学习和考试评价中的作用越来越多地受到史家、教师和命题者的重视．</p></div>
     </div>
     <div class="user2">
     <div class="userp2"> <img src="@/assets/team2.png" alt=""></div>
     <div class="userinfo2"><p>英国历史学家彼德·伯克在《图像证史》一书中力图说明的基本论点是:图像如同文本和口述证词一样,也是历史证据的一种重要形式．"左图右书"也是我国古代治史传统．近年来,画作、地图、历史事件及实物的照片等可视材料在史学研究、历史学习和考试评价中的作用越来越多地受到史家、教师和命题者的重视．</p></div>
     </div>
     <div class="user3">
     <div class="userp3"> <img src="@/assets/team3.png" alt=""></div>
     <div class="userinfo3"><p>英国历史学家彼德·伯克在《图像证史》一书中力图说明的基本论点是:图像如同文本和口述证词一样,也是历史证据的一种重要形式．"左图右书"也是我国古代治史传统．近年来,画作、地图、历史事件及实物的照片等可视材料在史学研究、历史学习和考试评价中的作用越来越多地受到史家、教师和命题者的重视．</p></div>
     </div>
     </div>
  </div>
</ScaleBox>
</template>

<style>
    .tabout {
      min-width: 1903px;
      min-height: 850px;
      display: block;
      align-items: center;
      background-color: rgb(249, 251, 253);
    }
    .ttitle {
      width: 230px;
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
    .ttheme {
      min-width: 1500px;
      display: inline-block;
      margin-left: 250px;
      height: 50px;
      font-family: Lato Black;
      font-size: 36px;
      font-weight: bolder;
    } 
    .tinfo {
      min-width: 1600px;
      width: 70%;
      height: 90%;
      float: left;
      margin-top: 10px;
      margin-left: 15%;
    }
    .user1 {
      width: 300px;
      height: 700px;
      float: left;
      position: relative;
      margin-right: 70px;
    }
    .userp1 {
      position: absolute;
      z-index: 10;
    }
    .userp1 img{
      display: block;
      width: 200px;
      height: 200px;
    }
    .userinfo1{
      display: block;
      position: absolute;
      width: 350px;
      height: 500px;
      margin-top: 150px;
      background-image: url(../assets/team.jpg);
      background-size: 100%;
    }
    .userinfo1 p{
      margin-top: 90px;
      padding-left: 20px;
      padding-right: 30px;
      font-family: Lao UI;
      font-size: 18px;
      text-align: left;
      color: rgb(59, 75, 90);
      border-radius: 10px;
      font-weight: bolder;
      text-decoration: underline
    }
    .user2 {
      width: 300px;
      height: 700px;
      float: left;
      position: relative;
      margin-right: 70px;
    }
    .userp2 {
      position: absolute;
      margin-left: 100px;
      z-index: 10;
    }
    .userp2 img{
      display: block;
      width: 200px;
      height: 200px;
    }
    .userinfo2 {
      display: block;
      position: absolute;
      width: 350px;
      height: 500px;
      margin-top: 150px;
      margin-left: 100px;
      background-image: url(../assets/team.jpg);
      background-size: 100%;
    }
    .userinfo2 p{
      margin-top: 90px;
      padding-left: 20px;
      padding-right: 30px;
      font-family: Lao UI;
      font-size: 18px;
      text-align: left;
      color: rgb(59, 75, 90);
      border-radius: 10px;
      font-weight: bolder;
      text-decoration: underline
    }
    .user3 {
      width: 300px;
      height: 700px;
      float: left;
      position: relative;
      margin-right: 70px;
      margin-left: 100px;
    }
    .userp3 {
      position: absolute;
      margin-left: 100px;
      z-index: 10;
    }
    .userp3 img{
      display: block;
      width: 200px;
      height: 200px;
    }
    .userinfo3{
      display: block;
      position: absolute;
      width: 350px;
      height: 500px;
      margin-top: 150px;
      margin-left: 100px;
      background-image: url(../assets/team.jpg);
      background-size: 100%;
    }
    .userinfo3 p{
      margin-top: 90px;
      font-family: Lao UI;
      padding-left: 20px;
      padding-right: 30px;
      font-size: 18px;
      text-align: left;
      color: rgb(59, 75, 90);
      border-radius: 10px;
      font-weight: bolder;
      text-decoration: underline
    }
</style>
