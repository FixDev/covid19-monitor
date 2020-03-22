<template>
      <b-card bg-variant="warning" text-variant="white" header="Positif" class="text-center">
        <b-card-text>{{ positif.value }} Jiwa</b-card-text>
      </b-card>
</template>

<script>
export default {
  data() {
    return {
      positif: []
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      const res = await this.$axios.get(
        "https://covid19.mathdro.id/api"
      );
      this.positif = res.data.confirmed;

    }
  }
};
</script>

<style></style>
