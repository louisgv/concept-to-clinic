<template>
<form-wizard>
  <tab-content title="Personal details">
    My first tab content
  </tab-content>
  <tab-content title="Additional Info">
    My second tab content
  </tab-content>
  <tab-content title="Last step">
    Yuhuuu! This seems pretty damn simple
  </tab-content>
</form-wizard>
</template>

<script>
import {
  FormWizard,
  TabContent
} from 'vue-form-wizard'

export default {
  components: {
    FormWizard,
    TabContent
  },
  props: ['label', 'value', 'constant-key'],
  computed: {
    constantValue: function () {
      return this.$constants[this.constantKey][this.value]
    }
  }
}
</script>

<style lang="scss" scoped>
p label {
    font-weight: bold;
}
</style>
