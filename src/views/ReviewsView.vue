
<script setup lang="ts">
import { computed, ref } from 'vue'
import axios from "axios"
import TestJson from "@/review.json";

const count = ref([
  {
    title: '● Human papillomavirus integration perspective in small cell cervical carcinoma',
    url: 'https://www.nature.com/articles/s41467-022-33359-w'
  },
  {
    title: '● System and method for enabling the secure storage, transmission and access of genetic data',
    url: 'https://patents.glgoo.top/patent/US11451522B2/en'
  },
  {
    title: '● Nucleophilicity Prediction Using Graph Neural Networks',
    url: 'https://pubs.acs.org/doi/abs/10.1021/acs.jcim.2c00696'
  },
  {
    title: '● SPROUT: spectral sparsification helps restore the spatial structure at single-cell resolution',
    url: 'https://watermark.silverchair.com/lqac069.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAAsswggLHBgkqhkiG9w0BBwagggK4MIICtAIBADCCAq0GCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQM3dxG1FvHv7hRU4huAgEQgIICfvgrDI_oEmU5hduN0FukqOThAN3NiJKBJa7-wmaZyQFvFwy-KRNDRuiLYnyB4oMtkATGPMh8seEnup-P-SJ6YM6c4ZmisXEg4Aj5nJ4FmyFvy7psuBR6yTJ4n7Rt4v-Pq9tPZEF6QCDt_OrZ6vdtDJkCj1v1ztqzXlYB6gWcfX4fqAdBUsrNzPZb71ql7ySw2jvt5tUuTrH5pHHDQp3FY3VCXrFYLxoxm3lGCVd2VkuAAZAN1Cyb-cXZKELpQbNm7KflptVUDsReGHYq8Cye19faRMpVFA8PXtYbaN1kqGKCZZs22P5FH2GyccZo6rsSZTeHKqfks355R6qVcmS7KTJ86ABKuLX1lKqPX6B539UPrlillZn9KixOCoOdUVTB6mfgfTp7qUz4jcQu8lT6GjC_HhIBuAUyFcahSsyRVcnX9d6iSI4qADS8_nq8C59g9GL9ak44pKQ9U7_wF-OIB12of6s5ORbkJkDlES_-ttnI2y2UdIzAUopz0SRGfGCtJsmEIDsdmmioYrp3OqBbRSqboC6RFbCZM0d_Ihm2OFD-s6k9TcKV2TWIC5hGNy-cW5LwUIbutK73ZPZj-rBfDutIfTgw1L5jIvtbX6yl7S5Bfg3Dbo2fwUNbH5CrnVPpFCviSUyWi_goOLRC0KlIuy7DbKP1Wz_cuChMJrS7HgwFWVdBzF3r3PHf-jLzQ8HJwdvkjiOU61FTOP1qHtLhN5hfmIKJyxOYYeqinIzauWwP5OYQZH5dVjChxltUs5YcGMg5h0wMK8NsGEehogwM8onpFaBwo29KrhA-XZMHcFwKzfxxXC_W1x1wwGWCGLnTcb5CFThCClvP7KuxYQIF'
  },
  {
    title: '● Mining bacterial NGS data vastly expands the complete genomes of temperate phages',
    url: 'https://watermark.silverchair.com/lqac057.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAAsswggLHBgkqhkiG9w0BBwagggK4MIICtAIBADCCAq0GCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQMZ288bYRKOu1rYl7iAgEQgIICfprAJt4CG1Z6XszPUweVxg9qpYRNcpP9sNvCOg7yHNaDqrJo1cvr0VtGjC3kWnolS3EtvyqR8BOE8S_IhiU7pbwCKookNgCqK5nqEVVlXNEp7cJpNL7ffm7qjYo0vnZH7BprwNdHAEgXCLaKjInnJiw9AJq5517GYBIDIMuUY7gv-9x_kcC_auFq3rm8DFOoLRuD1a9b-0rIvqT5xHFxQuhSxhKtAEhW4NISfnJuyJd8g5SZ1Zn8pA32TQBTTXX6Rma9Ca1WyQ5zaQcgaf9wIYx2bsJEFNJG5OTOxOsQ-zD-qq2b7mbUIGeVnw4lPWBndeDiEZ_orn9dmnrPtnzluTEwe4Y9_9gAxNGNqOgDZXaIJ0w72XcoHImGfT26kamUZXg_UN_YxzyCXvCA_2f-DbTv-Ak2PLM101UIGeVG6BEueFO9qQikq4GgR9VpR9gcX7Abpjjvih6dIill7fvJgSwZbMMJUiaGtZ-skboHgS09UHecEmYveF6v3_U_Es9vNXvE4A3djcZ4scBgdq2j1AoY-dqljTYMUAXnCjBAqTodIBW1EO8J9tqqSWul8XSagvAtQMXdT0eUvzDqgIzfNFUiTxjr4PuUmQrHzZ_OnrT2TrXHa9pMLknY5zbybQWqXRmLJ0OY0WiV3Ggf_8uAq56a6f6HQF0jNdAxM6RWW8no-25ivOm7UQmPbB1v3jOqd4vOQyb1N4VMAbPRa3YMcAk58mfDmNQWIKjx93GanKWXzi_KZlf8B9E8cVs0rZV6f8vn-nsdTr8wBxCr-kzoWvsi1F-UP6wAG4S6SOrAKitqkPcW-cBkrQVTESAIbfPa_IV2OyBffDB9oTDdp-To'
  },
  {
    title: '● Resolving single-cell copy number profiling for large datasets',
    url: 'https://academic.oup.com/bib/article-abstract/23/4/bbac264/6633647'
  },
  {
    title: '● Detecting TAD-like domains from RNA-associated interactions',
    url: 'https://academic.oup.com/nar/advance-article-abstract/doi/10.1093/nar/gkac422/6593122'
  },
  {
    title: '● The Tibetan-Yi region is both a corridor and a barrier for human gene flow',
    url: 'https://www.sciencedirect.com/science/article/pii/S2211124722004818'
  },
  {
    title: '● Altered metabolome and microbiome features provide clues in understanding irritable bowel syndrome and depression comorbidity',
    url: 'https://www.nature.com/articles/s41396-021-01123-5'
  },
  {
    title: '● Microbiome resilience and health implications for people in half-year travel',
    url: 'https://www.frontiersin.org/articles/10.3389/fimmu.2022.848994/pdf'
  },
  {
    title: '● Dynamic changes of gut microbiota and hepatic functions are different among biliary atresia patients after Kasai portoenterostomy',
    url: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8858627/'
  },
  {
    title: '● Periodontal and peri-implant microbiome dysbiosis is associated with alterations in the microbial community structure and local stability',
    url: 'https://www.frontiersin.org/articles/10.3389/fmicb.2021.785191/pdf'
  },
  {
    title: '● PRCTC: a machine learning model for prediction of response to corticosteroid therapy in COVID-19 patients',
    url: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8791209/'
  },
  {
    title: '● Cervicovaginal microbiota significantly changed for HPV-positive women with high-grade squamous intraepithelial lesion',
    url: 'https://www.frontiersin.org/articles/10.3389/fcimb.2022.973875/full?utm_source=dlvr.it&utm_medium=twitter'
  },
  {
    title: '● Profiling the peripheral blood T cell receptor repertoires of gastric cancer patients',
    url: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9367216/'
  },
  {
    title: '● Both simulation and sequencing data reveal coinfections with multiple SARS-CoV-2 variants in the COVID-19 pandemic',
    url: 'https://www.sciencedirect.com/science/article/pii/S2001037022000861'
  },
  {
    title: '● Over‐shedding of donor‐derived cell‐free DNA at immune‐related regions into plasma of lung transplant recipient',
    url: 'https://onlinelibrary.wiley.com/doi/full/10.1002/ctm2.622'
  },
  {
    title: '● Somatic variant analysis suite: copy number variation clonal visualization online platform for large-scale single-cell genomics',
    url: ''
  },
  {
    title: '● DeepHost: phage host prediction with convolutional neural network',
    url: 'https://academic.oup.com/bib/article-abstract/23/1/bbab385/6374063'
  },
  {
    title: '● Functional organization of the maternal and paternal human 4d nucleome',
    url: 'https://www.sciencedirect.com/science/article/pii/S2589004221014231'
  },
  {
    title: '● Longitudinal virological changes and underlying pathogenesis in hospitalized COVID-19 patients in Guangzhou, China',
    url: 'https://link.springer.com/article/10.1007/s11427-020-1921-5'
  },
  {
    title: '● Development and validation of an online model to predict critical COVID-19 with immune-inflammatory parameters',
    url: 'https://jintensivecare.biomedcentral.com/articles/10.1186/s40560-021-00531-1'
  },
  {
    title: '● SuperTAD: robust detection of hierarchical topologically associated domains with optimized structural information',
    url: 'https://genomebiology.biomedcentral.com/articles/10.1186/s13059-020-02234-6'
  },
  {
    title: '● Alteration of the respiratory microbiome in COVID-19 patients with different severities',
    url: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8595322/'
  },
  {
    title: '● The genome variation and developmental transcriptome maps reveal genetic differentiation of skeletal muscle in pigs',
    url: 'https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1009910'
  },
  {
    title: '● SpecHap: a diploid phasing algorithm based on spectral graph theory',
    url: 'https://academic.oup.com/nar/article/49/19/e114/6353808'
  },
  {
    title: '● Resolving complex structures at oncovirus integration loci with conjugate graph',
    url: 'https://academic.oup.com/bib/article-abstract/22/6/bbab359/6359003'
  },
  {
    title: '● Differential perturbations of gut microbial profiles and co‐occurrence networks among phases of methamphetamine‐induced conditioned place preference',
    url: 'https://onlinelibrary.wiley.com/doi/abs/10.1002/jnr.24963'
  },
  {
    title: '● Deep learning model reveals potential risk genes for ADHD, especially Ephrin receptor gene EPHA5',
    url: 'https://academic.oup.com/bib/article/22/6/bbab207/6295376'
  },
  {
    title: '● SCYN: Single cell CNV profiling method using dynamic programming',
    url: 'https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-021-07941-3'
  },
  {
    title: '● Whole‐genome sequencing identifies novel candidate pathogenic variants associated with left ventricular non‐compaction in a three‐generation family',
    url: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8351521/'
  },
  {
    title: '● Metagenomic Sequencing Reveals Distinct Microbial Community Structures in Healthy and Diseased Oral Microbiota',
    url: 'https://scholar.archive.org/work/3q2vonoxnvh2bbgoxxf3tbz45q/access/wayback/https://assets.researchsquare.com/files/rs-694037/v1/68f34fc2-5327-4cd9-860f-73fb2935903c.pdf?c=1626291285'
  },
  {
    title: '● Development and Validation of a Machine Learning Model for Prediction of Response to Corticosteroid Therapy In COVID-19 Patients',
    url: 'https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3834263'
  },
  {
    title: '● Limits to the cellular control of sequestered cryptophyte prey in the marine ciliate Mesodinium rubrum',
    url: 'https://www.nature.com/articles/s41396-020-00830-9'
  },
  {
    title: '● PStrain: an iterative microbial strains profiling algorithm for shotgun metagenomic sequencing data',
    url: 'https://academic.oup.com/bioinformatics/article-abstract/36/22-23/5499/6042705'
  },
  {
    title: '● Computational Methods in Inferring Cancer Tissue-of-Origin and Cancer Molecular Classification',
    url: 'https://www.frontiersin.org/articles/10.3389/fgene.2021.644542/full'
  },
  {
    title: '● Altered nitric oxide induced by gut microbiota reveals the connection between central precocious puberty and obesity',
    url: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7842634/'
  },
  {
    title: '● Bacterial Signatures of Paediatric Respiratory Disease: An Individual Participant Data Meta-Analysis',
    url: 'https://www.frontiersin.org/articles/10.3389/fmicb.2021.711134/full?&utm_source=Email_to_authors_&utm_medium=Email&utm_content=T1_11.5e1_author&utm_campaign=Email_publication&field=&journalName=Frontiers_in_Microbiology&id=711134'
  },
  {
    title: '● Association between metabolic status and gut microbiome in obese populations',
    url: 'https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8549370/'
  },
  {
    title: '● Transcriptome Atlas of 16 Donkey Tissues',
    url: 'https://www.frontiersin.org/articles/10.3389/fgene.2021.682734/full'
  },
  {
    title: '● Cervicovaginal Microbiome Factors in Clearance of Human Papillomavirus Infection',
    url: 'https://www.frontiersin.org/articles/10.3389/fonc.2021.722639/full'
  },
  {
    title: '● Donkey genomes provide new insights into domestication and selection for coat color',
    url: 'https://www.nature.com/articles/s41467-020-19813-7'
  },
  {
    title: '● LDscaff: LD-based scaffolding of de novo genome assemblies',
    url: 'https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-020-03895-7'
  },
  {
    title: '● Deep learning for HGT insertion sites recognition',
    url: 'https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-020-07296-1'
  },
  {
    title: '● Breastfeeding restored the gut microbiota in caesarean section infants and lowered the infection risk in early life',
    url: 'https://bmcpediatr.biomedcentral.com/articles/10.1186/s12887-020-02433-x'
  },
  {
    title: '● A comprehensive investigation of metagenome assembly by linked-read sequencing',
    url: 'https://link.springer.com/article/10.1186/s40168-020-00929-3;'
  },
  {
    title: '● Understanding Horizontal Gene Transfer network in human gut microbiota',
    url: 'https://gutpathogens.biomedcentral.com/articles/10.1186/s13099-020-00370-9'
  },
  {
    title: '● Is antibiotics prescription needed in infants with topical corticosteroids treatment for moderate‐to‐severe atopic dermatitis?',
    url: 'https://onlinelibrary.wiley.com/doi/abs/10.1111/dth.14215'
  },
  {
    title: '● I-Impute: a self-consistent method to impute single cell RNA sequencing data',
    url: 'https://link.springer.com/article/10.1186/s12864-020-07007-w'
  },
  {
    title: '● Diagnosis and prognosis prediction of ovarian cancer with feedforward neural network by mining real-world laboratory tests',
    url: 'https://sgo.confex.com/sgo/2020/meetingapp.cgi/Paper/16878'
  },
  {
    title: '● CIRPMC: An online model with simplified inflammatory signature to predict the occurrence of critical illness in patients with COVID‐19',
    url: 'https://onlinelibrary.wiley.com/doi/full/10.1002/ctm2.210'
  },
  {
    title: '● Distinct skin microbiota imbalance and responses to clinical treatment in children with atopic dermatitis',
    url: 'https://www.frontiersin.org/articles/10.3389/fcimb.2020.00336/full'
  },
  {
    title: '● Establishing high-accuracy biomarkers for colorectal cancer by comparing fecal microbiomes in patients with healthy families',
    url: 'https://www.tandfonline.com/doi/full/10.1080/19490976.2020.1712986'
  },
  {
    title: '● Oviz-Bio: a web-based platform for interactive cancer genomics data visualization',
    url: 'https://academic.oup.com/nar/article/48/W1/W415/5835823'
  },
  {
    title: '● Different nasopharynx and oropharynx microbiota imbalance in children with Mycoplasma pneumoniae or influenza virus infection',
    url: 'https://www.sciencedirect.com/science/article/abs/pii/S0882401020304769'
  },
  {
    title: '● Genome architecture and transcription data reveal allelic bias during the cell cycle',
    url: 'https://scholar.archive.org/work/vcm4cuxuk5exzcvmrrxootg2yy/access/wayback/https://www.biorxiv.org/content/biorxiv/early/2020/03/17/2020.03.15.992164.full.pdf'
  },
  {
    title: '● Heterogeneity of immune microenvironment in ovarian cancer and its clinical significance: a retrospective study',
    url: 'https://www.tandfonline.com/doi/full/10.1080/2162402X.2020.1760067'
  },
  {
    title: '● CovProfile: profiling the viral genome and gene expressions of SARS-COV-2',
    url: 'https://www.biorxiv.org/content/10.1101/2020.04.05.026146v2.abstract'
  },

]);
const count1 = TestJson.links;
const size = ref(14)
console.log(count1.length)
// const1 size = ref(14)
// const list = ref(count.value.slice(0,size.value))
const list = ref(count1.slice(0,size.value))
const noMore = computed(() => size.value >= count.value.length)
const disabled = computed(() => noMore.value)
const load = () => {
size.value += count1.length-14
list.value = count1.slice(0, size.value)
}
const reload = () => {
size.value = 14
list.value = count1.slice(0, size.value)
}
</script>


<template>
  <div class="rabout">
    <div class="rtitle">RESULTS</div>
    <div class="rtheme">Publications</div>
    <div class="rinfo">
      <div class="rinco"><img src="@/assets/ricon.png" alt=""></div>
      <div class="rlist">
        <ul  class="infinite-list" style="overflow: auto">
          <li v-for="item,index in list" class="infinite-list-item"><a :href=item.url target="_Blank">{{ item.title }}</a> 
          </li>
        </ul>
        <p v-if="!noMore" @click="load" style="padding-top: 10px;"><a>more...</a></p>
        <p v-if="noMore" @click="reload" style="padding-top: 10px;"><a>retract</a></p>
      </div>
      <div class="rlistimg">
        <div class="rlist1"><img src="@/assets/rlist/rlist1.png" alt=""></div>
        <div class="rlist2"><img src="@/assets/rlist/rlist2.png" alt=""></div>
        <div class="rlist3"><img src="@/assets/rlist/rlist3.png" alt=""></div>
        <div class="rlist4"><img src="@/assets/rlist/rlist4.png" alt=""></div>
        <div class="rlist5"><img src="@/assets/rlist/rlist5.png" alt=""></div>
        <div class="rlist6"><img src="@/assets/rlist/rlist6.png" alt=""></div>
        <div class="rlist7"><img src="@/assets/rlist/rlist7.png" alt=""></div>
        <div class="rlist8"><img src="@/assets/rlist/rlist8.png" alt=""></div>
      </div>
      <div>
      </div>
    </div>
  </div>
</template>

<style>
.rabout {
  min-width: 1903px;
  min-height: 850px;
  display: block;
  align-items: center;
  background-color: rgb(249, 251, 253);
}

.rtitle {
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

.rtheme {
  min-width: 1500px;
  display: inline-block;
  margin-left: 250px;
  height: 50px;
  font-family: Lato Black;
  font-size: 36px;
  font-weight: bolder;
}

.rinfo {
  min-width: 1600px;
  height: 90%;
  float: left;
  margin-left: 150px;
  margin-top: 10px;
}

.rinco {
  height: 50px;
  width: 50px;
  float: left;
}

.rinco img {
  height: 50px;
  width: 50px;
}

.rlist {
  margin-left: 10px;
  width: 600px;
  float: left;
}

.infinite-list {
  height: 600px;
  padding: 0;
  margin: 0;
}

.infinite-list .infinite-list-item {
  width: 600px;
  font-size: 15px;
  float: left;
  padding-top: 2px;
}

p{
  font-size: 15px;
}


.rlistimg {
  float: left;
  width: 700px;
  height: 700px;
  margin-left: 150px;
  background-image: url(../assets/rlistimg_b.png);
  background-size: 100%;
  position: relative;
}

.rlist1 {
  margin-top: 50px;
  margin-left: 50px;
  position: absolute;

}
.rlist1 img{
  width: 159px;
}

.rlist2 {
  position: absolute;
  margin-top: 200px;
}
.rlist2 img{
  width: 175px;
}
.rlist3 {
  margin-left: 200px;
  position: absolute;
}
.rlist3 img{
  width: 213px;
}
.rlist4 {
  margin-top: 150px;
  margin-left: 450px;
  position: absolute;
}
.rlist4 img{
  width: 202px;
}
.rlist5 {
  margin-top: 320px;
  margin-left: 100px;
  position: absolute;
}
.rlist5 img{
  width: 205px;
}
.rlist6 {
  margin-top: 150px;
  margin-left: 220px;
  position: absolute;
}
.rlist6 img{
  width: 281px;
}
.rlist7 {
  margin-top: 400px;
  margin-left: 500px;
  position: absolute;

}
.rlist7 img{
  width: 225px;
}
.rlist8 {
  margin-top: 300px;
  margin-left: 570px;
  position: absolute;
}
.rlist8 img{
  width: 197px;
}
.ttt {
  list-style-type: disc !important;
}</style>
