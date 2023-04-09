<script setup lang="ts">
</script>
<template>
  <div class="habout">
  <div class="htitle"><img src="@/assets/htitle.svg" alt=""></div>
  <div class="hinfo">Omiclab Limited—a high-tech enterprise developing bioinformatics algorithms, 
  AI models and implementing the methods on biotech multi-omics sequencing data. 
  The core team is comprised of Ph.Ds from top-rank universities (QS rank &lt 60) with rich experiences in the fields of life science,
   genome sequencing and bioinformatics. The team have published more than 200 SCI papers,
    with many of them published in top journals including PNAS, Nature Communications, Nature Genetics, Nucleotide Acid Research and Bioinformatics.
</div>
  </div>
</template>

<style>
    .habout {
      width: 100%;
      min-height: 850px;
      /* display: block; */
      align-items: center;
      background-image: url('../assets/background.png') ;
      background-size: cover;
    }
    .htitle {
      padding-top: 200px;
      margin-left: 30%;
    }
    .htitle img{
     width: 574px;
    }
    .hinfo{
      margin-top: 50px;
      width: 800px;
      font-size: 17px;
      color: rgb(223, 239, 251);
      margin-left: 30%;
    }
</style>
