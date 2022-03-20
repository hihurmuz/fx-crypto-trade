<template>
	<v-container>
		<v-btn  class="my-8" color="success" elevation="0" @click="$router.push('/bots/add-new')">Add New</v-btn>
		<div>No matching records found</div>
	</v-container>
</template>

<script>
export default {
	name: "bots"
}
</script>

