<template>
<div class="offset-top container">
  <div class="row">
    <div class='col-md-3'>
      <outline-nav :outlines="outlines" v-model="activeOutlineId"></outline-nav>
    </div>

    <div class='col-md-9'>
      <rsna-standard-template
        v-show="activeOutlineId === '#RSNA'"
        :rsna="study"
        :nodules="nodules">
      </rsna-standard-template>

      <acr-lung-rad-findings
        v-show="activeOutlineId === '#ACR'">
      </acr-lung-rad-findings>

      <export-3d-imagery
        v-show="activeOutlineId === '#Export3D'">
      </export-3d-imagery>

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
import OutlineNav from '../components/report-and-export/OutlineNav'

import RSNAStandardTemplate from '../components/report-and-export/RSNAStandardTemplate'
import ACRLungRADFindings from '../components/report-and-export/ACRLungRADFindings'
import Export3DImagery from '../components/report-and-export/Export3DImagery'

export default {
  components: {
    OutlineNav,
    'rsna-standard-template': RSNAStandardTemplate,
    'acr-lung-rad-findings': ACRLungRADFindings,
    'export-3d-imagery': Export3DImagery
  },
  data () {
    return {
      activeOutlineId: '#RSNA',
      outlines: [
        // {
        //   name: 'Overview',
        //   id: '#Overview'
        // },
        {
          name: 'RSNA Standard Template',
          id: '#RSNA'
        },
        {
          name: 'ACR Lung-RAD™ Findings',
          id: '#ACR'
        },
        {
          name: 'Export 3D Imagery',
          id: '#Export3D'
        }
      ],
      study: {
        technical: [
          {
            name: 'kVp',
            value: 120
          },
          {
            name: 'mA',
            value: 93
          },
          {
            name: 'DLP',
            value: 18,
            unit: 'µSv/mGy'
          }
        ],
        clinical: [
          {
            name: 'Screening Visit',
            value: 'Year 1'
          },
          {
            name: 'Clinical Information',
            value: 'Lung cancer screening'
          }
        ],
        screeningVisit: 'Year 1',
        clinicalInformation: 'Lung cancer screening',
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
