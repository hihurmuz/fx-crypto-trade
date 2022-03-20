<template>
	<v-card elevation="0" outlined>
		<v-container>
			<v-row class="px-2" align="center">
				<v-checkbox
					v-model="checkbox"
				/>
				<h3>Trailing Stop</h3>
			</v-row>
			<div v-show="checkbox">
				<v-row>
					<v-col>
						Trailing Stop Activation
						<v-text-field number />
					</v-col>
					<v-col>
						Trailing Stop Execute
						<v-text-field number />
					</v-col>
				</v-row>
			</div>
		</v-container>
	</v-card>
</template>

<script>
export default {
	name: "TrailingStop",
	data() {
		return {
			checkbox: false,
		}
	}
}
</script>

<style scoped>

</style>
