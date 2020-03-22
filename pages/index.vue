<template>
  <no-ssr>
    <div>
      <b-container>
        <b-row>
          <h4 class="mx-auto">Covid19 Monitoring Global</h4>
        </b-row>
        <br />
        <b-card-group deck>
          <Positif />
          <Recovered />
          <Deaths />
        </b-card-group>
        <br />
        <div class="grid mx-auto">
          <ChartBar />
          <br />
          <Indonesia />
          <ChartIndonesia />
        </div>
      </b-container>
    </div>
  </no-ssr>
</template>

<script>
import Positif from "~/components/global/positif.vue";
import Recovered from "~/components/global/recovered.vue";
import Deaths from "~/components/global/deaths.vue";
import Indonesia from "~/components/indonesia/indonesia.vue";
import ChartBar from "@/components/chart/chart.vue";
import ChartIndonesia from "@/components/chart/chartIndonesia.vue";

export default {
  components: {
    Positif,
    Recovered,
    Deaths,
    Indonesia,
    ChartBar,
    ChartIndonesia
  }
};
</script>

<style>
h4 {
  margin: auto;
  padding: 10px;
}
,
.grid {
  display: grid;
  row-gap: 2rem;
}
</style>
