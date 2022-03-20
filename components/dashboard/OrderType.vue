<template>
	<v-card elevation="0" outlined>
		<v-container>

			<v-row>
				<v-col>
					<h3 class="mb-4">Order Type</h3>
					<v-btn color="primary" elevation :outlined="type === 'market'" @click="type = 'market'">Market</v-btn>
					<v-btn color="primary" elevation :outlined="type === 'limit'" @click="type = 'limit'">Limit</v-btn>
					<v-btn color="primary" elevation :outlined="type === 'stop-limit'" @click="type = 'stop-limit'">Stop Limit</v-btn>
				</v-col>
				<v-col>
					<h3>Price</h3>
					<v-text-field v-model="price" />
				</v-col>
			</v-row>

			<v-row v-if="type == 'limit'">
				<v-col>
					<h3>Time in force</h3>
					<div>Time in minutes before Limit order expires (5-5000 min)</div>
					<v-select />
				</v-col>
			</v-row>

			<v-row v-if="type == 'stop-limit'">
				<v-col>
					<h3>Stop Price</h3>
					<v-text-field v-model="stopPrice" />
				</v-col>
			</v-row>
		</v-container>
	</v-card>
</template>

<script>
export default {
	name: "OrderType",
	data() {
		return {
			type: 'market',
			price: '0.00000000',
			stopPrice: '0.00000000',
		}
	}
}
</script>

<style scoped>

</style>
