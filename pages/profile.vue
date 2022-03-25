<template>
	<v-container>
		<v-col class="px-0" cols="12" md="6">
			<div class="text-h6">Change Name</div>
			<div class="primary--text">Fill the field below and save:</div>
			<v-text-field class="mt-0 pt-0" />
			<div class="text-h6">Write about you</div>
			<div class="primary--text">Write about you and save so other users can read it:</div>
			<v-text-field class="mt-0 pt-0"/>
			<div class="text-h6">Change default page</div>
			<div class="primary--text">Choose default page for your cabinet:</div>
			<v-select class="mt-0 pt-0"/>
			<div class="text-h6">Time zone</div>
			<div class="primary--text">Select the city of your timezone:</div>
			<v-select class="mt-0 pt-0"/>
		</v-col>
	</v-container>
</template>

<script>
export default {
	name: "profile",
	data() {
		return {
			tab: null,
			text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
		}
	}
}
</script>

<style scoped>

</style>
