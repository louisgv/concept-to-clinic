<template>
<div class="rsna-standard-template-container">
  <header class="bg-inverse">
    <h1>
      RSNA Standard Template
    </h1>
    <button class="btn btn-lg btn-warning">
      Export
    </button>
  </header>

  <section id="technical-parameters">
    <h2>Technical parameters</h2>

    <div class="technical-card-container">
      <technical-card v-for="(item, index) in rsna.technical"
        :key="item.name"
        :detail="item"
        :style="{background: technicalBackground[index]}">
      </technical-card>
    </div>

  </section>

  <section id="clinical-information">
    <h2>Clinical information</h2>
    <div class="technical-card-container">
      <technical-card v-for="(item, index) in rsna.clinical"
        :key="item.name"
        :detail="item"
        :style="{
          width: '45%',
          height: '18em',
          background: technicalBackground[index]
        }"></technical-card>
    </div>
  </section>

  <section id="findings">
    <h2>Findings</h2>

    <h3>Exam parameters</h3>
    <li>Diagnostic quality: {{ rsna.diagnosticQuality }}</li>
    <li>Comments: {{ rsna.examParametersComment }}</li>

    <h3>Lung nodules</h3>

    <li v-for='nodule in nodules'>
      <a href='#' @click='selectSeries(series)'>{{ series.series_instance_uid }}</a>
      <span v-if='series == selected'>&larr;</span>
    </li>

    <h4>Lungs</h4>
    <li>COPD: {{ rsna.COPD }}</li>
    <li>Filiosis: {{ rsna.filiosis }}</li>
    <li>Lymph nodes: {{ rsna.lymphNodes }}</li>
    <li>Other findings: {{ rsna.otherFindings }}</li>

    <h4>Right pleural space</h4>
    <li>Effusion: {{ rsna.rightPleuralSpace.effusion }}</li>
    <li>Calcification: {{ rsna.rightPleuralSpace.calcification }}</li>
    <li>Thickening: {{ rsna.rightPleuralSpace.thickening }}</li>
    <li>Pneumothorax: {{ rsna.rightPleuralSpace.pneumothorax }}</li>

    <h4>Left pleural space</h4>
    <li>Effusion: {{ rsna.rightPleuralSpace.effusion }}</li>
    <li>Calcification: {{ rsna.rightPleuralSpace.calcification }}</li>
    <li>Thickening: {{ rsna.rightPleuralSpace.thickening }}</li>
    <li>Pneumothorax: {{ rsna.rightPleuralSpace.pneumothorax }}</li>

    <h4>Heart</h4>
    <li>Heart size: {{ rsna.heartSize }}</li>
    <li>Coronary calcification: {{ rsna.coronaryCalcification }}</li>
    <li>Pericardial effusion: {{ rsna.pericardialEffusion }}</li>

    <h4>Other</h4>
    <li>Upper abdomen: {{ rsna.upper_abdomen }}</li>
    <li>Thorax: {{ rsna.thorax }}</li>
    <li>Base of neck: {{ rsna.base_of_neck }}</li>
    <h2>Impression</h2>
    <li>Need comparison: {{ rsna.need_comparison }}</li>
    <li>Repeat CT: {{ rsna.repeatCT }}</li>
    <li>See physician: {{ rsna.see_physician }}</li>
    <li>{{ rsna.impressionComment }}</li>
  </section>
</div>
</template>

<script>
import TechnicalCard from './TechnicalCard'

export default {
  components: {
    TechnicalCard
  },
  data () {
    return {
      technicalBackground: ['#60D9F1', '#5770F9', '#453DF4']
    }
  },
  props: [ 'rsna', 'nodules' ],
  methods: {

  }
}
</script>

<style lang="scss" scoped>
.rsna-standard-template-container {

  header {
    display: flex;
    justify-content: space-between;;
    align-items: center;
    color: white;
    padding-left: 2em;
    font-weight: normal;
    letter-spacing: 2px;
		margin-bottom: 10px;

    padding-right: 10%;

    h1 {
      font-size: 2.5em;

      line-height: 2em;
      margin: 0;
    }

  }

  h2 {
    padding-top: 0.5em;
    padding-left: 1em;
    margin-bottom: 0.5em;
  }

  section {
    margin-bottom: 3em;
  }

  .technical-card-container {
    display: flex;
    justify-content: space-around;
  }
}
</style>
