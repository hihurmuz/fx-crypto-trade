<template>
	<v-card elevation="0" outlined>
		<v-container>
			<h3>Portfolio size</h3>
			<v-row>
				<v-col>
					Portfolio size
					<v-text-field v-model="size" number />
				</v-col>
				<v-col>
					Amount in quote currency
					<v-select />
				</v-col>
			</v-row>
			<v-row class="mt-0 mb-2 px-1">
				<v-chip
					v-for="(el,i) in autoSize"
					:key="i"
					class="mx-2"
					:color="el == size && 'primary'"
					@click="size = el"
				>
					{{ el }}%
				</v-chip>
			</v-row>
		</v-container>
	</v-card>
</template>

<script>
export default {
	name: "PortfolioSize",
	data() {
		return {
			size: 25,
			autoSize: [10, 25, 50,75,100]
		}
	}
}
</script>

<style scoped>

</style>
