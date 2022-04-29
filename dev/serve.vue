<script>
import Vue from 'vue'
import IeAlert from '@/ie-alert.vue'

export default Vue.extend({
	name: 'ServeDev',
	components: {
		IeAlert,
	},
})
</script>

<template>
	<div id="app">
		<ie-alert always-visible />
	</div>
</template>
