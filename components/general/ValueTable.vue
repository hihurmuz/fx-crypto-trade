<template>
	<table class="value-table">
		<tr>
			<th>USDT</th>
			<th>BTC</th>
			<th>ETH</th>
		</tr>
		<tr >
			<td>0.00 $</td>
			<td>0.00000000</td>
			<td>0.00000000</td>
		</tr>
	</table>
</template>

<script>
export default {
	name: "ValueTable"
}
</script>

<style scoped>
th, td {
	border: 1px solid #dee2e6;;
	padding: 10px 70px 10px 10px;
	text-align: left;
}

tr > th {
	font-weight: 900;
}
.value-table {
	border-collapse: collapse;
}
</style>
