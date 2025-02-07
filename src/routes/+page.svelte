<script lang="ts">
	import { TableHandler } from '@vincjo/datatables';

	let { data } = $props();

	const table = new TableHandler(data.items, { rowsPerPage: 50 });
</script>

data:
<pre> {JSON.stringify(data.items)}</pre>

<table>
	<thead>
		<tr>
			<th>First name</th>
			<th>Last name</th>
			<th>Gender</th>
			<th>Age</th>
			<th>Email</th>
			<th>Phone</th>
		</tr>
	</thead>
	<tbody>
		{#each table.rows as row}
			<tr>
				<td>{row.firstName}</td>
				<td>{row.lastName}</td>
				<td>{row.gender}</td>
				<td>{row.age}</td>
				<td>{row.email}</td>
				<td>{row.phone}</td>
			</tr>
		{/each}
	</tbody>
</table>
