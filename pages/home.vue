<template>
	<div class="d-flex flex-wrap"
		 color="grey lighten-2">
		<info-card class="ma-4" v-for="(el,i) in infoCardData" :key="i" :info="el"/>
	</div>
</template>

<script>
export default {
	name: 'Home',
	data() {
		return {
			infoCardData:[
				{
					title: "My Exchange",
					content: "Connect an exchange using API Key or manage\n" +
						"already connected exchange accounts.",
					buttons: [
						{
							title: "Manage",
							path: "/"
						},
						{
							title: "Connect an exchange",
							path: "/"
						}
					]
				},
				{
					title: "Terminal",
					content: "Flexible way of creating orders for smart trading:\n" +
						"adding and editing Take Profit, Stop Loss and\n" +
						"Trailing stops to any order.",
					buttons: [
						{
							title: "Create a trade",
							path: "/"
						},
					]
				},
				{
					title: "Bots",
					content: "WunderTrading will help you to automate any\n" +
						"Trading View scripts into the fully functioning\n" +
						"crypto trading bot.",
					buttons: [
						{
							title: "Create a Bot",
							path: "/"
						},
						{
							title: "Manage",
							path: "/"
						},
					]
				},
			]
		}
	}
}
</script>

