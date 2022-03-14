<template>
	<v-app>
		<general-menu/>
		<v-main>
			<v-container>
				<Nuxt/>
			</v-container>
		</v-main>
		<general-footer/>
	</v-app>
</template>

<script>
export default {
	data() {
		return {
			clipped: false,
			drawer: true,
		}
	}
}
</script>
