<template>
	<v-container>
		<v-row>
			<v-col>
				<VueTradingView
					:options="{
					  symbol: 'CRYPTOCAP:XMR',
					  theme: 'dark',
					}"
				/>

			</v-col>
			<v-col>
				<BuySellCard />
				<AvailablePairs class="my-5" />
				<OrderType class="my-5"/>
				<PortfolioSize class="my-5" />
				<TakeProfit class="my-5" :number="1" />
				<TakeProfit class="my-5" :number="2" />
				<TakeProfit class="my-5" :number="3" />
				<TrailingStop class="my-5" />
				<v-btn color="primary" elevation block x-large>Create A Strategy</v-btn>
			</v-col>
		</v-row>

	</v-container>
</template>

<script>
import VueTradingView from 'vue-trading-view';
import BuySellCard from "@/components/dashboard/BuySellCard";
import AvailablePairs from "@/components/dashboard/AvailablePairs";
import OrderType from "@/components/dashboard/OrderType";
import PortfolioSize from "@/components/dashboard/PortfolioSize";
import TakeProfit from "@/components/dashboard/TakeProfit";
import TrailingStop from "@/components/dashboard/TrailingStop";

export default {
	name: "terminal",
	components: {
		TrailingStop,
		TakeProfit,
		PortfolioSize,
		OrderType,
		AvailablePairs,
		BuySellCard,
		VueTradingView,
	}
}
</script>
