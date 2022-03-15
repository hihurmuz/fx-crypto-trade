<template>
	<v-card
		class="pa-6"
		elevation="0"
		outlined
		max-width="500"
	>
		<v-row class="ma-0 pa-0">
			<v-icon>mdi-check</v-icon>
			<h3>{{ info.title }}</h3>
		</v-row>
		<p>
			{{ info.content }}
		</p>
		<v-btn class="mr-2" color="primary" outlined large v-for="(el,i) in info.buttons" :key="i" :to="el.path">
			{{ el.title }}
		</v-btn>
	</v-card>
</template>

<script>

export default {
	name: "InfoCard",
	props: {
		info: {
			type: Object,
			default: () => {
				return {
					title: "My Exchange",
					content: "Connect an exchange using API Key or manage\n" +
						"already connected exchange accounts.",
					buttons: [
						{
							title: "Manage",
							path: "/"
						}
					]
				}
			}
		},
	}
}
</script>

