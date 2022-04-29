<template>
	<div v-if="show || alwaysVisible" class="ie-alert-wrapper">
		<div v-if="showAlert" class="window">
			<div class="title-bar">
				<div class="title-bar-text">Nope</div>
				<div class="title-bar-controls">
					<button aria-label="Close" @click="showAlert = false"></button>
				</div>
			</div>
			<div class="window-body">
				<p>Nice try, but you can't just skip this.</p>
				<button @click="showAlert = false">Ok</button>
			</div>
		</div>
		<div v-else class="window" :style="{ width: maximized ? '100%' : '300px', height: maximized ? '100%' : 'auto' }">
			<div class="title-bar">
				<div class="title-bar-text">This Website Does Not Support Internet Explorer</div>
				<div class="title-bar-controls">
					<button aria-label="Maximize" @click="maximized = !maximized"></button>
					<button aria-label="Close" @click="showAlert = true"></button>
				</div>
			</div>
			<div class="window-body">
				<p>
					Unfortunately you can't view this website using the Internet Explorer.
				</p>
				<p>
					Despite the fact that most websites might not be working properly, using the Internet Explorer is a severe security threat.
				</p>
				<a href="https://support.microsoft.com/en-us/windows/internet-explorer-help-23360e49-9cd3-4dda-ba52-705336cc0de2">Find out more</a>
				<p style="font-weight: bold;">
					You should instead try one of the following browsers:
				</p>
				<button @click="goToFirefox">Mozilla Firefox</button>
				<button @click="goToChrome">Google Chrome</button>
				<button @click="goToEdge">Microsoft Edge</button>
			</div>
		</div>
	</div>
</template>

<script>
import '98.css'

export default /*#__PURE__*/ {
	name: 'IeAlert',
	props: {
		alwaysVisible: {
			type: Boolean,
			default: false,
		},
	},
	data: () => ({
		show: false,
		maximized: false,
		showAlert: false,
	}),
	mounted() {
		if (window.document.documentMode) {
			this.show = true
		}
	},
	methods: {
		goToFirefox() {
			window.location.href = 'https://firefox.com'
		},
		goToChrome() {
			window.location.href = 'https://chrome.google.com'
		},
		goToEdge() {
			window.location.href = 'https://edge.microsoft.com'
		},
	},
}
</script>

<style scoped>
.ie-alert-wrapper {
	position: fixed;
	top: 0;
	left: 0;
	right: 0;
	bottom: 0;
	display: flex;
	justify-content: center;
	align-items: center;
	background-color: #456ea6;
}
</style>
