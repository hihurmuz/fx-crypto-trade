<template>
	<v-container>
		<div class="text-h6 mt-10">Email preferences</div>
		<div class="primary--text mb-10">Please select which email notifications you would like to receive.</div>
		<table class="value-table">
			<tr>
				<th></th>
				<th>Strategy</th>
				<th>API account</th>
			</tr>
			<tr class="denenme">
				<td>Position entry</td>
				<td>
					<v-switch class="pa-0 "/>
				</td>
				<td>
					<v-switch class="pa-0 "/>
				</td>
			</tr>
			<tr>
				<td>Position exit</td>
				<td>
					<v-switch class="pa-0 "/>
				</td>
				<td>
					<v-switch class="pa-0 "/>
				</td>
			</tr>
			<tr>
				<td>Error notifications</td>
				<td>
					<v-switch class="pa-0 "/>
				</td>
				<td>
					<v-switch class="pa-0 "/>
				</td>
			</tr>
		</table>
	</v-container>
</template>

<script>
export default {
	name: "notifications"
}
</script>

<style scoped>
.value-table {
	border-collapse: collapse;
}

th, td {
	border: 1px solid #dee2e6;;
	padding: 10px 70px 10px 10px;
	text-align: left;
}

tr td:first-child {
	font-size: 16px;
	font-weight: bold;
}

tr > th {
	font-weight: 900;
}

</style>
