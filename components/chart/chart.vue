<template>
  <div class="card">
    <div class="card-body">
      <h2 class="card-title">Statistik Covid19 World</h2>
    </div>

    <div class="card-img-bottom">
      <canvas id="fooCanvas" count="3" />

      <chartjs-bar
        v-for="(item, index) in items"
        :key="index"
        :backgroundcolor="item.bgColor"
        :beginzero="beginZero"
        :bind="true"
        :bordercolor="item.borderColor"
        :data="item.data"
        :datalabel="item.dataLabel"
        :labels="labels"
        target="fooCanvas"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      beginZero: true,
      labels: ["Covid19 Statistik"],
      items: []
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      const res = await this.$axios.get("https://covid19.mathdro.id/api");

      this.items = [
        {
          bgColor: "yellow",
          borderColor: "0c0306",
          dataLabel: "Positif",
          data: [res.data.confirmed.value] 
        },
        {
          bgColor: "green",
          borderColor: "030c0c",
          data: [res.data.recovered.value],
          dataLabel: "Sembuh"
        },
        {
          bgColor: "red",
          borderColor: "030c0c",
          data: [res.data.deaths.value],
          dataLabel: "Meninggal"
        }
      ];
    }
  }
};
</script>
