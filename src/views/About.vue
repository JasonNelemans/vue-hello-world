<template>
  <div id="about">
    {{ info }}
  </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';

new Vue({
  el: '#about',
  data() {
    return {
      info: null,
    };
  },
  mounted() {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then((response) => (this.info = response));
  },
});
</script>
