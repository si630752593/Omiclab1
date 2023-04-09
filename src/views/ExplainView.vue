<script setup lang="ts">
</script>
<template>
<ScaleBox :width="1920" :height="1080" bgc="transparent" :delay="100">
  <div class="eabout">
    <div class="stitle">DETAILS</div>
    <div class="etheme">How does it work</div>
    <div class="einfo"> <img src="@/assets/einfo.png" alt=""></div>
  </div>
</ScaleBox>
</template>

<style>
    .eabout {
      width: 100%;
      min-height: 850px;
       display: block;
      align-items: center;
      background-color: rgb(249, 251, 253);
    }
    .stitle {
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
    .etheme {
      width: 80%;
      display: inline-block;
      font-family: Lato Black;
      font-size: 36px;
      margin-left: 12%;
      font-weight: bolder;
    }
    .einfo {
      width: 85%;
      height: 90%;
      float: left;
      margin-left: 8%;
      margin-top: 180px;
    }
    .einfo img{
      width: 100%;
      height: 90%;
    }
</style>
