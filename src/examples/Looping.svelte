<script lang="ts">
	const users = ['Bob', 'Alice', 'Dave', 'Eve']
</script>

<ul>
	{#each users as user, index}
		<li>
			{index}
			{user}
		</li>
	{/each}
</ul>
