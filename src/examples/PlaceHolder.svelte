<script lang="ts">
	import Code from '@lib/components/code.svelte'
	import HelloWorld from './HelloWorld.svelte'
	import { Stretch } from '@components'

	export let title = 'Anatomy of a .svelte file'
	export let isLarge = false
	export let showOutput = true

	export let replLink =
		'https://svelte.dev/repl/6c7d844b4ee64ebebcb402bfb184d72c?version=4.1.1'

	export let Component: typeof HelloWorld
	export let ComponentRaw: string
</script>

<Stretch>
	<p class="py-4">{title}</p>
	<div class="mx-auto flex items-center justify-center gap-4">
		<div class="overflow-scroll" class:text-lg={isLarge}>
			<Code lang="svelte">
				{ComponentRaw}
			</Code>
		</div>

		{#if showOutput}
			<div class="text-lg">
				<div
					class="grid place-items-center bg-slate-800 rounded-lg p-4 aspect-square h-[400px]"
				>
					<div>
						<svelte:component this={Component}></svelte:component>
					</div>
				</div>
				<div class="text-left">
					<a class="text-sm" href={replLink} target="_blank"> REPL </a>
				</div>
			</div>
		{/if}
	</div>
</Stretch>
