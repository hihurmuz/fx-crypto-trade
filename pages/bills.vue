<template>
	<v-container>
		<v-row class="px-3 mt-5">
			<v-btn text color="primary" outlined>Pricing</v-btn>
			<v-btn text color="primary">billing history</v-btn>
		</v-row>
		<v-row class="mt-8 ">
			<v-col>
				<v-card elevation="0" outlined width="300" height="100%">
					<v-card-text>
						Current Plan
					</v-card-text>
					<v-card-title>
						Free
					</v-card-title>
				</v-card>
			</v-col>
			<v-col>
				<v-card elevation="0" outlined width="300"  height="100%">
					<v-card-text>
						Promo Code
					</v-card-text>
					<v-row class="px-6" justify="space-between" align="center">
						<v-text-field class="mr-2" label="Enter Promo Code" />
						<v-btn color="primary" tile>Apply</v-btn>
					</v-row>
				</v-card>
			</v-col>
		</v-row>
		<v-row>
			<v-col v-for="(el,i) in productData" :key="i" cols="12" md="3" >
				<ProductCard  :card-info="el" />
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
import ProductCard from "@/components/ProductCard";

export default {
	name: "bills",
	components: {ProductCard},
	data() {
		return {
			productData: [
				{
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
					isSelected: false,
				},
				{
					title: "Basic",
					text: "Automate your trading and investment for passive income.",
					price: 9.95,
					features: [
						"15 open positions",
						"5 active bots",
						"2 API per exchange",
						"Trailing stop",
						"Multiple take profits",
						"DCA trading terminal",
					],
					isSelected: true,
				},
				{
					title: "Pro",
					text: "For full time traders to combine manual, automatic and copy-trading.",
					price: 24.95,
					features: [
						"100 open positions",
						"15 active bots",
						"5 API per exchange",
						"Fixed amount",
						"Spread trading terminal",
						"Swing trade",
					],
					isSelected: false,
				},
				{
					title: "Premium",
					text: "Unlimited features for traders and their followers.",
					price: 44.95,
					features: [
						"Unlimited open positions",
						"Unlimited active bots",
						"Unlimited API per exchange",
					],
					isSelected: false,
				},
			]
		}
	}
}
</script>

<style scoped>

</style>
