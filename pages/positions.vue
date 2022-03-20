<template>
	<v-container>
		<v-row class="my-8">
			<v-btn color="primary" :outlined="history" elevation @click="changePositionListType">Live</v-btn>
			<v-btn class="mx-4" color="primary" :outlined="!history" elevation @click="changePositionListType">History</v-btn>
		</v-row>
		<v-row class="my-8">
			<v-btn color="error" elevation @click="dialog = true" >Close All</v-btn>
		</v-row>
		<v-row>
			<v-data-table
				:headers="headers"
				:items="desserts"
				:items-per-page="5"
				class="elevation-2"
				outlined
			/>
		</v-row>
		<v-dialog
			v-model="dialog"
			max-width="540"
		>
			<v-card>
				<v-card-title class="text-h5 text-center">
					Are you sure you would like to close all open positions?
				</v-card-title>

				<v-card-actions class="d-flex flex-row justify-center">
					<v-btn
						color="primary"
						large
						@click="dialog = false"
					>
						Yes
					</v-btn>

					<v-btn
						color="primary"
						large
						@click="dialog = false"
					>
						No
					</v-btn>
				</v-card-actions>
			</v-card>
		</v-dialog>
	</v-container>
</template>

<script>
export default {
	name: "positions",
	data() {
		return {
			dialog: false,
			history: false,
			headers: [
				{
					text: 'Position',
					align: 'start',
					sortable: false,
					value: 'position',
				},
				{ text: 'Entry', value: 'entry' },
				{ text: 'Take Profit', value: 'take_profit' },
				{ text: 'Stop Loss', value: 'stop_loss' },
				{ text: 'Trailing Stop | Activation Price', value: 'trailing_stop' },
				{ text: 'Portfolio', value: 'Portfolio' },
				{ text: 'P/L', value: 'P/L' },
				{ text: 'ROI', value: 'ROI' },
				{ text: 'R/R', value: 'R/R' },
				{ text: 'Status', value: 'status' },
				{ text: 'Last Update', value: 'last_update' },
				{ text: 'Actions', value: 'actions' }
			],
			desserts: [

			]
		}
	},
	methods: {
		changePositionListType() {
			this.history = !this.history
		}
	}
}
</script>

