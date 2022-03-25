<template>
	<v-card min-height="100%" class="w-100 pa-4 " :class="{'selected-product': cardInfo.isSelected}" outlined elevation>
		<div class="text-center">
			<div class="text-h2 font-weight-regular">{{ cardInfo.title }}</div>
			<div class="primary--text">{{ cardInfo.text }}</div>
		</div>

		<div class="text-center my-16">
			<h2>$ {{ cardInfo.price }}</h2>
			<div>USD / 1 Ay</div>
		</div>

		<div v-if="cardInfo.price !== 0.00" class="d-flex flex-row justify-center my-16">
			<v-btn color="primary" outlined tile>Upgrade</v-btn>
		</div>


		<div>
			<h6>Top features</h6>
			<div v-for="i in cardInfo.features" :key="i">
				<v-icon color="success">
					mdi-check-circle
				</v-icon>
				{{ i }}
			</div>
		</div>
	</v-card>
</template>

<script>
export default {
	name: "ProductCard",
	props: {
		cardInfo: {
			type: Object,
			default: () => {
				return {
					title: "Free",
					text: "Explore crypto trading automation for free.",
					price: 0.00,
					features: [
						"5 open positions",
						"2 active bots",
						"1 API per exchange",
						"Trading Terminal (Spot Trading, Futures Trading)",
						"Spot Trading",
						"Futures Trading",
						"Simultaneous Take Profit and Stop Loss",
					],
					isSelected: false
				}
			}
		}
	}
}
</script>

<style scoped>
.selected-product.v-sheet.v-card {
	border: 5px solid #94e394;
}
</style>

