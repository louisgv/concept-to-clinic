<template>
<div class="offset-top">
  <div class="outline-nav">
		<h1>Outline</h1>
    <ul>
      <li v-for='outline in outlines'>
        <a href='#' @click='jumpToOutline(outline)'>{{ outline }}</a>
      </li>
    </ul>
  </div>

  <rsna-standard-template :rsna="study" :nodules="nodules"></rsna-standard-template>

</div>
</template>

<script>
import RSNAStandardTemplate from '../components/RSNAStandardTemplate'

export default {
  components: {
    'rsna-standard-template': RSNAStandardTemplate
  },
  data () {
    return {
      outlines: ['Overview', 'RSNAStandardTemplate', 'ACR Lung-RAD tm Findings', 'Export 3D Imagery'],
      study: {
        kVp: null,
        mA: null,
        DLP: null,
        screeningVisit: 'BL',
        clinicalInformation: '',
        comparison: 'null',
        diagnosticQuality: 'SF',
        examParametersComment: '',
        COPD: 0,
        filiosis: 0,
        lymphNodes: 'null.',
        otherFindings: 'null.',
        rightPleuralSpace: {
          effusion: 0,
          calcification: 0,
          thickening: 0,
          pneumothorax: 0
        },
        leftPleuralSpace: {
          effusion: 0,
          calcification: 0,
          thickening: 0,
          pneumothorax: 0
        },
        heartSize: 0,
        coronaryCalcification: 0,
        pericardialEffusion: 0,
        upperAbdomen: 'null',
        thorax: 'null',
        baseOfNeck: 'null',
        needComparison: 'No',
        repeatCT: 'T1',
        seePhysician: 'NO',
        impressionComment: ''
      },
      nodules: []
    }
  }
}
</script>

<style media="screen">
.offset-top {
  margin-top: 5em;
}

@media screen and (max-width: 990px) {
  .offset-top {
    margin-top: 10em;
  }
}
</style>
