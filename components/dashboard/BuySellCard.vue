<template>
	<v-card elevation="0" outlined>
		<v-container>
			<v-row>
				<v-col>
					Exchange
					<v-select />
				</v-col>
				<v-col>
					API
					<v-select />
				</v-col>
			</v-row>
			<v-row>
				<v-col>
					<h4>Strategy Type</h4>
					<v-row>
						<v-col>
							<v-btn color="primary" :outlined="classic" @click="classic = !classic">Classic</v-btn>
							<v-btn color="primary" :outlined="!classic" @click="classic = !classic">DCA</v-btn>
						</v-col>
					</v-row>
				</v-col>
			</v-row>
			<v-row>
				<v-col><v-btn block x-large color="success" :outlined="buy" @click="buy = !buy">Buy / Long</v-btn></v-col>
				<v-col><v-btn block x-large color="error" :outlined="!buy" @click="buy = !buy">Sell / Short</v-btn></v-col>
			</v-row>
		</v-container>
	</v-card>
</template>

<script>
export default {
	name: "BuySellCard",
	data() {
		return {
			classic: true,
			buy: true
		}
	}
}
</script>
