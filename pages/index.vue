<template>
	<v-row justify="center" align="center">
		<v-col class="mt-16" cols="12" sm="12" md="12">
			<TheLoginCard />
		</v-col>
	</v-row>
</template>
<script>
import TheLoginCard from "@/components/general/TheLoginCard";
export default {
	components: {TheLoginCard},
	layout: 'login'

}
</script>
