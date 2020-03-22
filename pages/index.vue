<template>
  <div>
    <b-card-group deck>
      <b-card
        v-for="item in items"
        :key="item.value"
        border-variant="primary"
        header="Confirmed"
        header-bg-variant="primary"
        header-text-variant="white"
        align="center"
      >
        <b-card-text>{{ item.value }}</b-card-text>
        <b-card-text>{{ item.detail }}</b-card-text>
      </b-card>
    </b-card-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: []
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      const res = await this.$axios.get("https://covid19.mathdro.id/api/");
      this.items = res.data;
    }
  }
};
</script>

<style></style>
