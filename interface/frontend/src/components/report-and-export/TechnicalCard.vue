<template lang="html">

	<div class="technical-card">
		<label>{{label}}</label>
		<h2>{{value}}</h2>
	</div>
</template>

<script>
export default {
  props: ['label', 'value']
}
</script>

<style lang="scss">
.technical-card {

	width: 270px;
	height: 135px;
	background: #4C8DDA;

	label {
		position: absolute;
		bottom: 0;
	}
}

</style>
