<template>
  <div class="container">
    <wizard-flow></wizard-flow>
    <image-series></image-series>
  </div>
</template>

<script>
import WizardFlow from '../components/common/WizardFlow'
import ImageSeries from '../components/open-image/ImageSeries'

export default {
  name: 'open-image',
  components: {
    ImageSeries,
    WizardFlow
  }
}
</script>

<style lang="scss" scoped>
</style>
