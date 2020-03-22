<template>
  <b-card
    bg-variant="success"
    text-variant="white"
    header="Sembuh"
    class="text-center"
  >
    <b-card-text>{{ recovered.value }} Jiwa</b-card-text>
  </b-card>
</template>

<script>
export default {
  data() {
    return {
      recovered: []
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      const res = await this.$axios.get("https://covid19.mathdro.id/api");
      this.recovered = res.data.recovered;
    }
  }
};
</script>

<style></style>
