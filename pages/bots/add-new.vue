<template>
	<v-container>
		<v-row>
			<v-col>
				<v-card elevation outlined tile>
					<v-container>
						<v-row>
							<v-col>
								<h3>Bot Name</h3>
								<div>
									Enter Bot name (do not use underscore sign or spaces, use dash sign)
								</div>
								<v-text-field v-model="botName"/>
								<h3>Bot Description</h3>
								<v-text-field />
								<v-row>
									<v-col>
										<h3>Exchange</h3>
										<v-select />
									</v-col>
									<v-col>
										<h3>API</h3>
										<v-select />
									</v-col>
								</v-row>

								<h3>Time Frame</h3>
								<v-row>
									<v-col>
										<v-text-field />
									</v-col>
									<v-col>
										<v-select />
									</v-col>
									<v-col>
										<v-select />
									</v-col>
								</v-row>

								<h3>Available pairs</h3>
								<div>
									You can trade only those pairs where you have balance above zero
								</div>
								<v-select />
							</v-col>
						</v-row>
					</v-container>
				</v-card>
				<TakeProfit class="my-5" :number="1" />
				<TakeProfit class="my-5" :number="2" />
				<TakeProfit class="my-5" :number="3" />
				<TrailingStop class="my-5" />
				<v-card class="my-5" color="red lighten-4" elevation outlined tile>
					<v-container>
						<h5>Important! Secure your Trading Bots with 2FA!</h5>
					</v-container>
				</v-card>
				<v-btn color="primary" outlined elevation block x-large>Create Bot Strategy</v-btn>
			</v-col>
			<v-col>
				<v-card color="red lighten-4" elevation outlined tile>
					<v-container>
						<h2>Attention!</h2>
						<b>
							Please notice that signal codes format was updated, new codes are available below. <br/>
							Please start using new codes in TradingView scripts as soon as possible.
						</b>

						<div class="mt-4">
							Carefully insert the message into the field and make sure that it is linked to the appropriate signal.
							The failure to do that may result in incorrect strategy execution.
						</div>

					</v-container>
				</v-card>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
import OrderType from "@/components/dashboard/OrderType";
import TakeProfit from "@/components/dashboard/TakeProfit";
import TrailingStop from "@/components/dashboard/TrailingStop";
export default {
	name: "add-new",
	components: {TrailingStop, TakeProfit, OrderType},
	data() {
		return {
			botName: 'Bot Name'
		}
	}
}
</script>

<style scoped>

</style>
