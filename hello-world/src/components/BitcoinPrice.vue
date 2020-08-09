<template>
  <div>
    <h1>Bitcoin Price Index</h1>
    <div v-for="currency in info" class="currency" :key="currency.description">
      {{ currency.description }}:
      <span class="lighten">
        <span v-html="currency.symbol"></span>
        {{ currency.rate_float | currencydecimal }}
      </span>
    </div>
  </div>
</template>
<script>
const axios = require("axios");

export default {
  name: "BitcoinPrice",
  data: function () {
    return {
      info: null,
    };
  },
  mounted() {
    this.getBitcoinPrice();
  },
  filters: {
    currencydecimal(value) {
      return value.toFixed(2);
    },
  },
  methods: {
    getBitcoinPrice: function () {
      axios
        .get("https://api.coindesk.com/v1/bpi/currentprice.json")
        .then((response) => (this.info = response.data.bpi));
    },
  },
};
</script>