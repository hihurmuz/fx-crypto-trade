<template>
	<v-app>
		<TheMenu />
		<v-main>
			<v-container>
				<Nuxt/>
			</v-container>
		</v-main>
		<Footer />
	</v-app>
</template>

<script>
import Footer from "@/components/general/Footer";
import TheMenu from "@/components/general/Menu";
export default {
	components: {TheMenu, Footer},
	data() {
		return {
			clipped: false,
			drawer: true,
		}
	}
}
</script>
