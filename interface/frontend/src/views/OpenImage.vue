<template>
<div class="container">
  <wizard-flow :steps="steps">
    <image-series slot="main-content"></image-series>
  </wizard-flow>
</div>
</template>

<script>
import {
  mapGetters
} from 'vuex'

import WizardFlow from '../components/common/WizardFlow'
import ImageSeries from '../components/open-image/ImageSeries'

export default {
  name: 'open-image',
  components: {
    ImageSeries,
    WizardFlow
  },
  computed: {
    ...mapGetters({
      imageInProgress: 'imageInProgress',
      caseInProgress: 'caseInProgress',
      caseInProgressIsValid: 'caseInProgressIsValid',
      candidatesExist: 'candidatesExist'
    }),
    steps () {
      return [{
        name: 'Select a Case or Import Imagery',
        active: this.candidatesExist && this.caseInProgress
      },
      {
        name: 'Create a new Case',
        active: this.imageInProgress.id || this.candidatesExist
      },
      {
        name: 'Case is Ready',
        active: this.candidatesExist
      }]
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
