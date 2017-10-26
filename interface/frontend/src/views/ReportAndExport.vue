<template>
<div class="offset-top container">
  <div class="row">
    <div class='col-md-3'>

      <outline-nav :outlines="outlines"></outline-nav>

    </div>

    <div class='col-md-9'>
      <rsna-standard-template :rsna="study" :nodules="nodules"></rsna-standard-template>
    </div>

  </div>

</div>
</template>

<style media="screen" lang="scss" scoped>
.offset-top {
    margin-top: 5em;
}
@media screen and (max-width: 990px) {
    .offset-top {
        margin-top: 10em;
    }
}
</style>

<script>
import RSNAStandardTemplate from '../components/report-and-export/RSNAStandardTemplate'
import OutlineNav from '../components/report-and-export/OutlineNav'

export default {
  components: {
    'rsna-standard-template': RSNAStandardTemplate,
    OutlineNav
  },
  data () {
    return {
      outlines: [ 'Overview', 'RSNA Standard Template', 'ACR Lung-RAD™ Findings', 'Export 3D Imagery' ],
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
