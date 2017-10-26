<template>
<div class="rsna-standard-template-container">
  <header>
    <h1>RSNA Standard Template</h1>
  </header>

  <section id="technical-parameters">
    <h2>Technical parameters</h2>

    <div class="technical-card-container">
      <technical-card label='kVp' :value='rsna.kVp'></technical-card>
      <technical-card label='mA' :value='rsna.mA'></technical-card>
      <technical-card label='DLP' :value='rsna.DLP'></technical-card>
    </div>

  </section>

  <section id="clinical-information">
    <h2>Clinical information</h2>
    <li>Screening visit: {{ rsna.screeningVisit }}</li>
    <li>{{ rsna.clinicalInformation }}</li>
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
  props: [ 'rsna', 'nodules' ],
  methods: {

  }
}
</script>

<style lang="scss" scoped>
.rsna-standard-template-container {



	#technical-parameters {


		.technical-card-container {
			display: flex;
			justify-content: space-around;
		}
	}
}
</style>
