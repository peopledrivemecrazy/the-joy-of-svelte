<script>
	import { count } from './store'
</script>

<button on:click={() => ($count += 1)}>
	{$count}
</button>
