<script>
import Vue from 'vue';
// Uncomment import and local "components" registration if library is not registered globally.
// import { DadaUiUiSample } from '@/entry.esm';

export default Vue.extend({
  name: 'ServeDev',
  // components: {
  //  DadaUiUiSample,
  // }
  methods: {
    testClick() {
      alert('dada button');
    },
  },
});
</script>

<template>
  <div id="app">
    <dada-ui-sample />
    <DadaButton label="dadaButton" primary size="medium" @click="testClick"/>
  </div>
</template>
