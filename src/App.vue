<script setup lang="ts">

import { nextTick, ref, render } from 'vue'
import Graph from 'graphology'
import Sigma from 'sigma'
import { Coordinates, EdgeDisplayData, NodeDisplayData } from "sigma/types"
import data from "../assets/graph.json"

const container = ref();
const graph = new Graph();
graph.import(data);
let sigma: Sigma;
nextTick(() => {
  sigma = new Sigma(graph, container.value as HTMLElement, {
    //minCameraRatio: 0.1,
    //maxCameraRatio: 10,
  })
});



</script>

<template>
  <div ref="container" class="container"></div>
</template>

<style>
.container {
  position: fixed;
  width: 100vw;
  height: 100vh;
  border: 2px solid black;
}

</style>
