<template>
  <div id="app">
    <topheader></topheader>

    <b-container>
      <b-row align-v="center">
        <card></card>
      </b-row>
    </b-container>
    
  </div>
</template>

<script>

import TopHeader from '@/components/TopHeader.vue';
import Card from '@/components/Card.vue';

export default { 
  components: 
  {
    "topheader":TopHeader,
    "card": Card,
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
