<template>
	<v-card elevation="0" outlined>
		<v-container>
			<h3>Available pairs</h3>
			<v-row>
				<v-col>
					<div>You can trade only those pairs where you have balance above zero</div>
					<v-select />
				</v-col>
			</v-row>
		</v-container>
	</v-card>
</template>

<script>
export default {
	name: "AvailablePairs"
}
</script>

<style scoped>

</style>
