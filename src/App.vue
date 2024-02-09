<script setup lang="ts">
import MainLayout from "@/components/MainLayout.vue";
import TrialMap from "@/components/trial-map.vue";
import Classify from "@/components/Classify.vue";
import ClassifyLegend from "@/components/ClassifyLegend.vue";

</script>

<template>
  <MainLayout>
    <div>
      <trial-map></trial-map>
    </div>


    <section class="max-w-[1280px] p-5 mx-auto">
      <p class="text-sm leading-7">
        Clara bog is one of the largest raised bogs in Ireland located in County Offlay. Only two thirds of the bog remain, with a third
        having been degraded to peat extraction. It covers around 840 hectares of which 443.36ha is uncut high bog while 393.18ha mostly cutover bog. Initially the bog was a dome shaped but currently
        two dome shapes. The construction of the Clara to Rahan road lead to its subsidence by 6 metres.
      </p>
      <div class="my-5">
        <div class="grid grid-cols-2  border">
          <div class="grid">
            <img src="@/assets/Clara_bog.png" alt="Clara Bog" class="w-full">
          </div>
          <div class="grid">
            <img src="@/assets/clara_change.png" alt="Clara Bog" class="w-full h-full">
          </div>

        </div>
        <p class="text-sm mt-3">
          Source: <a target="_blank" href="https://www.raisedbogs.ie/life-project/" class="underline text-blue-800">https://www.raisedbogs.ie/life-project/</a>
          Transformation of Clara bog between 1809 and 2006
        </p>
      </div>

      <div class="my-5">
        <p class="my-3">
         Peatlands are the only land-based solution to sequester carbon and hence their protection is paramount in climate change mitigation.
          They are often overlooked in detailed spatial documentation compared to significant land use changes, having suffered extensive drainage for human needs, 
          impacting greenhouse gas emissions and ecological balance. This projectcontributes to geographic knowledge by mapping the evolution of Clara peat bog. 
          
        </p>
        <div class="grid grid-cols-2 my-3">
          <div>
            <p class="leading-relaxed">
              Leveraging Landsat 5 and 8 in the Google Earth Engine application, the study utilizes NDVI and NDWI analysis to discern degradation, revegetation, and rewetting 
          restoration efforts.The composite images undergo comprehensive support vector machine and random forest classification over a five-decade timeframe from 1988, 1995, 2004, 
              2009, 2016 and 2023. Ecotope datasets are used for data training and validation. 
              Two predictive models were then created using python pickle libraries that predicted classification for other years. The accuracy of the classification
              models is evaluated using metrics such as Kappa, overall accuracy, and Producer accuracy. To enhance accessibility and visualisation, an analysis app
              within GEE and a dedicated monitoring website are developed, providing interactive tools for stakeholders.
            </p>

          </div>
          <div class="grid  gap-3">
            <img src="@/assets/problem_statement.png" alt="Problem statement" class="w-full ">
          </div>

        </div>

      </div>

    </section>
    <section class="max-w-[1280px] p-5 mx-auto">
      <h2 class="text-lg font-bold text-center my-3">Random Forest supervised classification</h2>
      <div class="my-5 grid grid-cols-3 gap-2">
        <div>
          <Classify year="1988" data-link="./data/Clara_1988.geojson"></Classify>
        </div>
        <div>
          <Classify year="1995" data-link="./data/Clara_1995.geojson"></Classify>
        </div>
        <div>
          <Classify year="2004" data-link="./data/Clara_2004.geojson"></Classify>
        </div>
        <div>
          <Classify year="2009" data-link="./data/Clara_2009.geojson"></Classify>
        </div>
        <div>
          <Classify year="2016" data-link="./data/Clara_2016.geojson"></Classify>
        </div>
        <div>
          <Classify year="2023" data-link="./data/Clara_2023.geojson"></Classify>
        </div>
      </div>
      <div class="my-3">
        <ClassifyLegend></ClassifyLegend>
      </div>
      <div class="my-3 grid grid-cols-2 gap-2">
        <div>
          <p class="leading-relaxed">
            The best-supervised classification algorithm was determined as Random Forest Classification with and overall accuracy of 82% for 2004 and 82% for 2016.
            Peatland's health condition seemed to increase with an increase in Active flush, which experienced a significant increase from 2016 when the second restoration initiatives began, 
            indicating ongoing restoration efforts. Marginal and submarginal decreased indicating a decrease in the degradation and an increase in restoration efforts. Remote sensing is crucial in detecting patterns of earth observation and documenting high detail spatial changes. The results have highlighted
            the efforts of different institutions and projects, such as the EU Living project, funded by the EU Life Fund in collaboration with NPWS and National Heritage from 2016 to 2021. 
            Consistent & innovative approaches in the monitoring of peat bogs are important in the conservation and rejuvenation of peatland habitat with the goal of conserving environmental
            areas and climate change mitigation.
             </p>
        </div>
       <div>
         <img src="@/assets/change-detection.png"  alt="Clara bog change detection">
       </div>
      </div>
    </section>

  </MainLayout>
</template>

<style scoped>

</style>
