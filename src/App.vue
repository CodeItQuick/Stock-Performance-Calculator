<script setup>
import * as Plot from "@observablehq/plot";
import PlotFigure from "./components/PlotFigure.js";
import voo from "./assets/voo.json";
import qqqm from "./assets/qqqm.json";
</script>

<template>
  <h1>Plot + Vue</h1>
  <PlotFigure
      :options="{
      marks: [
        Plot.line(voo, {x: 'date', y: 'close', transform: (data, facets) => ({data: data.map((x) => ({...x, date: new Date(x.date)})), facets })}),
        Plot.line(qqqm, {x: 'date', y: 'close', transform: (data, facets) => ({data: data.map((x) => ({...x, date: new Date(x.date)})), facets })}),
      ],
    }"
  />
</template>
