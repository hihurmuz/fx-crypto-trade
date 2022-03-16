<template>
	<div>
		<h2>Analytics</h2>
		<v-tabs v-model="tab">
			<v-tab>
				<h3>Trade's API Accounts</h3>
			</v-tab>
			<v-tab>
				<h3>Trading Bots</h3>
			</v-tab>
		</v-tabs>

		<v-tabs-items v-model="tab">
			<v-tab-item>
				<div class="d-flex flex-nowrap">
					<v-select
						class="mx-4"
						:items="items"
						label="Last Week"
					/>
					<v-select
						class="mx-4"
						:items="items"
						label="Min Trades Quantity"
					/>
				</div>
			</v-tab-item>
			<v-tab-item>
				<v-row class="ma-0">
					<v-select
						class="mx-4"
						:items="items"
						label="Last Week"
					/>
					<v-select
						class="mx-4"
						:items="items"
						label="All Exchanges"
					/>
					<v-select
						class="mx-4"
						:items="items"
						label="All Pairs"
					/>
					<v-select
						class="mx-4"
						:items="items"
						label="All Timeframes"
					/>
					<v-select
						class="mx-4"
						:items="items"
						label="All Leverages"
					/>
					<v-select
						class="mx-4"
						:items="items"
						label="Min Trades Quantity"
					/>
				</v-row>
			</v-tab-item>
		</v-tabs-items>

		<v-btn color="primary" elevation="0">
			Filter
		</v-btn>
		<p class="mt-5">No matching records found</p>

		<v-row>
			<v-col>
				<h2>Portfolio Value</h2>
				<general-value-table/>
			</v-col>
			<v-col>
				<h2>Profit and Loss</h2>
				<general-value-table/>
			</v-col>
		</v-row>
		<v-btn class="mt-5 mb-10" color="success" elevation="0">
			Update
		</v-btn>

		<h2>Portfolio</h2>
		<v-tabs v-model="tab2">
			<v-tab>
				<h3>Assets</h3>
			</v-tab>
			<v-tab>
				<h3>Assets by Exchange</h3>
			</v-tab>
			<v-tab>
				<h3>API Profile</h3>
			</v-tab>
		</v-tabs>
		<v-tabs-items v-model="tab2">
			<v-tab-item v-for="i in 3">
				<v-row class="ma-0">
					<v-col>
						Total ($): 0.00  <v-btn class="mt-5" color="success" elevation="0">
						Update
					</v-btn>
					</v-col>
					<v-col>
						<table class="value-table">
							<tr>
								<th>Coin</th>
								<th>USD Value</th>
								<th>Amount</th>
							</tr>
						</table>
					</v-col>
				</v-row>
			</v-tab-item>
		</v-tabs-items>
	</div>
</template>

<script>
export default {
	name: "Analytics",
	data() {
		return {
			tab: null,
			tab2: null,
			items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
		}
	}
}
</script>

<style scoped>
h2 {
	font-size: 32px;
}
th, td {
	border: 1px solid #dee2e6;;
	padding: 10px 70px 10px 10px;
	text-align: left;
}

tr > th {
	font-weight: 900;
}
.value-table {
	border-collapse: collapse;
}
</style>

