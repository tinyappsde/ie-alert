### IE Alert

This little vue component is based on the [98.css library](https://github.com/jdan/98.css) and shows a nice Windows 98 style alert to visitors that are still using the Internet Explorer.

![image](https://res.craft.do/user/full/b3f422e9-9c7e-a694-bd22-70c7a941aa0a/doc/0744E34B-5C21-4014-BC14-AA834586AA40/9DC7551B-BF93-4AD8-84F6-1DCCBD62F5A9_2/Mq8uchbU1fFbqxhXcZMqm3pVtdoXOKnNietnymjU4fsz/CleanShot%202022-04-29%20at%2016.53.172x.png)

##### Installation

`yarn add @tinyapps/ie-alert` or `npm i @tinyapps/ie-alert`

##### Usage


```javascript
<template>
	<div id="app">
		<ie-alert />
		<!-- your app -->
	</div>
</template>

<script>
import Vue from 'vue'
import IeAlert from '@tinyapps/ie-alert'

export default {
	name: 'app',
	components: {
		IeAlert,
	},
}
</script>
```


You can also use `<ie-alert always-visible />` to test, always show the alert or combine it with your own `v-if` condition.

Make sure to use scoped styling for your app that doesn't overwrite the windows 98 styling of the alert.
