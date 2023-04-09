<script setup lang="ts">
</script>
<template>
  <ScaleBox :width="1920" :height="1080" bgc="transparent" :delay="100">
  <div class="puabout">
    <div class="putitle">SUSTENTATION</div>
    <div class="putheme">Collaborator</div>
    <div class="puinfo">
    <ul>
    <li><div class="puicon"><img src="@/assets/pu/pu1.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu2.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu3.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu4.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu5.png" alt=""></div></li>
    </ul>
    <ul>
    <li><div class="puicon"><img src="@/assets/pu/pu6.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu7.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu8.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu9.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu10.png" alt=""></div></li>
    </ul>
    <ul>
    <li><div class="puicon"><img src="@/assets/pu/pu11.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu12.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu13.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu14.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu15.png" alt=""></div></li>
    </ul>
    <ul>
    <li><div class="puicon"><img src="@/assets/pu/pu16.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu17.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu18.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu19.png" alt=""></div></li>
    <li><div class="puicon"><img src="@/assets/pu/pu20.png" alt=""></div></li>
    </ul>
    </div>
  </div>
</ScaleBox>
</template>

<style>
    .puabout {
      min-width: 1903px;
      min-height: 850px;
      display: block;
      align-items: center;
      background-color: rgb(249, 251, 253);
    }

    .putitle {
      width: 220px;
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

    .putheme {
      min-width: 1500px;
      display: inline-block;
      margin-left: 250px;
      height: 50px;
      font-family: Lato Black;
      font-size: 36px;
      font-weight: bolder;
      /* font-weight: 100; */
    }

    .puinfo {
      min-width: 1600px;
      height: 90%;
      float: left;
      margin-top: 20px;
      margin-left: 13%;
      margin-right: 10%;
    }

    .puinfo ul{
      width: 1600px;
      height: 150px;
      list-style: none;
      margin-left: 40px;
    }
    /* .puinfo ul li{
      margin-right: 30px;
    } */

    .puicon img{
      float: left;
      width: 138px;
      height: 136px;
      margin-right: 120px;
    }
</style>
