<template>
	<v-card elevation="0" outlined>
		<v-container>
			<v-row class="px-2" align="center">
				<v-checkbox
					v-model="checkbox"
				/>
				<h3>Take Profit {{number}}</h3>
			</v-row>
			<div v-show="checkbox">
				<v-row>
					<v-col>
						Position size
						<v-text-field v-model="size" number />
						<v-chip
							x-small
							v-for="(el,i) in autoSize"
							:key="i"
							class="mx-2"
							:color="el == size && 'primary'"
							@click="size = el"
						>
							{{ el }}%
						</v-chip>
					</v-col>
					<v-col>
						<div>
							Take Profit
							<v-text-field v-model="profit" number />
							<v-chip
								x-small
								v-for="(el,i) in autoSize"
								:key="i"
								class="mx-2"
								:color="el == profit && 'primary'"
								@click="profit = el"
							>
								{{ el }}%
							</v-chip>
						</div>
						<v-text-field
							class="mt-8"
							v-model="price"
							label="Price"
						/>
					</v-col>
				</v-row>
				<v-row class="mt-0 mb-2 px-1">

				</v-row>
			</div>
		</v-container>
	</v-card>
</template>

<script>

export default {
	name: "TakeProfit",
	props: {
		number: {
			type: Number,
			default: 1
		}
	},
	data() {
		return {
			checkbox: false,
			size: 0,
			profit:0,
			autoSize: [10, 25, 50,75,100],
			price: 0.00001
		}
	}
}
</script>

<style scoped>

</style>
