<template>
  <div>
      <b-row>
        <h4 class="mx-auto">Covid19 Monitoring Indonesia</h4>
      </b-row>
      <br />
      <b-card-group deck>
        <b-card
          bg-variant="warning"
          text-variant="white"
          header="Positif"
          class="text-center"
        >
          <b-card-text>{{ indonesia.positif }} Jiwa</b-card-text>
        </b-card>

        <b-card
          bg-variant="success"
          text-variant="white"
          header="Sembuh"
          class="text-center"
        >
          <b-card-text>{{ indonesia.sembuh }} Jiwa</b-card-text>
        </b-card>

        <b-card
          bg-variant="danger"
          text-variant="white"
          header="Meninggal"
          class="text-center"
        >
          <b-card-text>{{ indonesia.meninggal }} Jiwa</b-card-text>
        </b-card>
      </b-card-group>
    <br />
  </div>
</template>

<script>
export default {
  data() {
    return {
      indonesia: []
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      const res = await this.$axios.get(
        "https://api.kawalcorona.com/indonesia/"
      );
      this.indonesia = res.data[0];
    }
  }
};
</script>

<style></style>
