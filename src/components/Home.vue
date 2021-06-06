<template>
  <div>
    <p v-if="dataReady">
        {{data}}
    </p>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      data: "",
      dataReady: false,
    };
  },
   async mounted() {
       const response = await this.$axios.get('https://api.coindesk.com/v1/bpi/currentprice.json')
        this.data = JSON.stringify(response.data.bpi)
        this.dataReady = true
  },

  methods: {
    async fetchData() {
    },
  },
};
</script>

<style lang="scss" scoped>
</style>