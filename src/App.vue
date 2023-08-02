<template>
  <!-- we'll use this template tag for declaring our custom report html -->
  <div>Hi from LeanIX Custom Report</div>
  <div>{{ state }}</div>  
</template>

<script setup>
  // all the state variables and business logic will be declared here
  import '@leanix/reporting';
  import { ref } from 'vue'
  
  var state = ref('empty');

lx.init()
.then(function (setupInfo) {
  debugger;
  state = JSON.stringify(setupInfo.savedState?.customState);  
  var config = {
    };
    lx.publishState({"test":"test"});
    lx.ready(config);  
});  
</script>