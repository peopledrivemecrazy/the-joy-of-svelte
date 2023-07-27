<script lang="ts">
	import { Notes, Presentation, Slide } from '@components'

	import PlaceHolder from './examples/PlaceHolder.svelte'
	import HelloWorld from './examples/HelloWorld.svelte'
	import HelloWorldRaw from './examples/HelloWorld.svelte?raw'

	import ReactiveAssingments from './examples/ReactiveAssingments.svelte'

	import ReactiveAssingmentsRaw from './examples/ReactiveAssingments.svelte?raw'

	import ReactiveDeclaration from './examples/ReactiveDeclaration.svelte'
	import ReactiveDeclarationRaw from './examples/ReactiveDeclaration.svelte?raw'
	import ConditionalRendering from './examples/ConditionalRendering.svelte'
	import ConditionalRenderingRaw from './examples/ConditionalRendering.svelte?raw'
	import Looping from './examples/Looping.svelte'
	import LoopingRaw from './examples/Looping.svelte?raw'
	import Stores from './examples/Stores.svelte'
	import StoresRaw from './examples/Stores.svelte?raw'

	const examples = [
		{
			title: 'Anatomy of a .svelte file',
			Component: HelloWorld,
			ComponentRaw: HelloWorldRaw,
			showOutput: true,
			isLarge: false,
			replLink:
				'https://svelte.dev/repl/6c7d844b4ee64ebebcb402bfb184d72c?version=4.1.1',
		},
		{
			title: 'Reactivity out of the box',
			Component: ReactiveAssingments,
			ComponentRaw: ReactiveAssingmentsRaw,
			showOutput: true,
			isLarge: false,
			replLink: 'https://svelte.dev/examples/reactive-assignments',
		},
		{
			title: 'Reactive Declaration',
			Component: ReactiveDeclaration,
			ComponentRaw: ReactiveDeclarationRaw,
			showOutput: true,
			isLarge: true,
			replLink: 'https://svelte.dev/examples/reactive-declarations',
		},
		{
			title: 'Conditional Rendering',
			Component: ConditionalRendering,
			ComponentRaw: ConditionalRenderingRaw,
			showOutput: false,
			isLarge: false,
			replLink: 'https://svelte.dev/examples/else-blocks',
		},
		{
			title: 'Each Block',
			Component: Looping,
			ComponentRaw: LoopingRaw,
			showOutput: true,
			isLarge: false,
			replLink: 'https://svelte.dev/examples/else-blocks',
		},
		{
			title: 'Simple Stores',
			Component: Stores,
			ComponentRaw: StoresRaw,
			showOutput: true,
			isLarge: false,
			replLink:
				'https://svelte.dev/repl/d1343b69b62d41468bc01c0596f5fa3b?version=4.1.1',
		},
	]
</script>

<svelte:head>
	<title>The Joy of Svelte</title>
</svelte:head>
<Presentation>
	<Slide animate>
		<div class="grid gap-4">
			<p>The Joy of Svelte</p>
			<p class="text-3xl">Shriji Kondan Elangovan</p>
		</div>
	</Slide>
	<Slide>
		<div>
			<p>What is Svelte?</p>
			<p>A pragmatic way build apps with minimal code</p>
		</div>
	</Slide>

	<Slide>
		<div class="grid gap-10 justify-center">
			<div>
				<p>Why is it Pragmatic?</p>
			</div>
			<ul class="text-3xl text-left w-[600px]">
				<li>Svelte offers a style of describing templates which is clean.</li>
				<li>Ol' reliable html, css and js.</li>
				<li>Reactivity is slick.</li>
				<li>Built-in stores.</li>
			</ul>
		</div>
		<Notes>Apart from all these things, Svelte has no VDOM, build tool is vite</Notes>
	</Slide>

	<Slide>Basics</Slide>
	{#each examples as { title, Component, ComponentRaw, replLink, isLarge, showOutput }}
		<Slide animate>
			<PlaceHolder
				{title}
				{Component}
				{ComponentRaw}
				{isLarge}
				{replLink}
				{showOutput}
			/>
		</Slide>
	{/each}

	<Slide>
		<div class="grid gap-10 justify-center">
			<div>
				<p>Basics - Components</p>
			</div>
			<ul class="text-3xl text-left w-[600px]">
				<li>Props</li>
				<li>Bind variables</li>
				<li class="text-xs">
					<a
						href="https://svelte.dev/repl/e927477d8b52498188a2d647d714e23b?version=4.1.1"
						target="_blank">Demo in REPL</a
					>
				</li>
			</ul>
		</div>
	</Slide>

	<Slide>What is Sveltekit?</Slide>

	<Slide>
		<div class="grid gap-10 justify-center">
			<div>
				<p>Sveltekit is a metaframework</p>
			</div>
			<ul class="text-3xl text-left">
				<li>Nextjs is to react is what Sveltekit is to Svelte</li>
				<li>Svelte is a component framework, write reusable components</li>
				<li>Routing, SSR, CSR and other goodies</li>
				<li>Edge friendly deployment with use of Adapters</li>
			</ul>
		</div>
	</Slide>
	<Slide>
		<div class="grid gap-10 justify-center">
			<div>
				<p>Live demo - 1</p>
			</div>
			<ul class="text-3xl text-left w-[600px]">
				<li>Simple page that pulls data from an API</li>
				<li>Dynamic routing</li>
				<li>Accessing data via page store</li>
			</ul>
		</div>
	</Slide>
	<Slide>
		<div class="grid gap-10 justify-center">
			<div>
				<p>Live demo - 2</p>
			</div>
			<ul class="text-3xl text-left w-[600px]">
				<li>Todo app - progressing enhancement</li>
			</ul>
		</div>
	</Slide>

	<Slide>
		<div class="grid gap-10 justify-center">
			<div>
				<p>My thoughts...</p>
			</div>
			<ul class="text-3xl text-left">
				<li>Code with just html, css and javascript</li>
				<li>JSX feels wrong to me</li>
				<li>Reactivity is predictable, no weird hooks/context/store</li>
				<li>No dependency is shipped to the browser</li>
				<li>
					Styles work with <span
						class="font-mono bg-black p-2 text-xs rounded-lg"
						>{`<\style\><\/style\>`}</span
					> scoped, no css-in-js
				</li>
				<li>Less/no boilerplate, less code, less headache, errors and bugs</li>
				<li>
					Focus on releasing a feature than battle the framework for performance
				</li>
			</ul>
		</div>
	</Slide>

	<Slide>
		<div class="grid gap-10 justify-center">
			<div>
				<p>My biased thoughts and opinions...</p>
			</div>
			<ul class="text-3xl text-left grid gap-4">
				<li>
					The only people who like React are the ones that didn't begin web
					development with HTML and CSS. They directly began web dev with
					create-react-app.
				</li>
				<li>
					A framework should support HTML and CSS for webapps, the browser knows
					HTML and CSS!
				</li>
				<li>Transitions built-in, no styled-components or other weird libs</li>
			</ul>
		</div>
	</Slide>
	<Slide animate>
		<div class="grid gap-10 justify-center">
			<div>
				<p>My biased thoughts and opinions...</p>
			</div>
			<ul class="text-3xl text-left grid gap-4">
				<li>
					Myth: Large enterprise scale applications can only be built with react
					and angular
				</li>
				<li>
					Myth: Svelte has no typescript support (recent news, svelte's code
					base was changed to JSDoc for skipping the entire build step for the
					svelte's core team)
				</li>
				<li>
					Learning Svelte has no job opportunities!?? - Learning won't replace
					your knowledge in react or angular
				</li>
			</ul>
		</div>
	</Slide>
	<Slide animate>
		<div class="grid gap-10 justify-center">
			<p>Resources</p>
			<p>svelte.dev</p>
			<p>kit.svelte.dev</p>
			<p>learn.svelte.dev</p>
		</div>
	</Slide>
	<Slide>
		<div class="grid gap-10">
			<p>Thank you!</p>

			<p>x.com/shriji</p>
		</div>
	</Slide>
</Presentation>

<style>
</style>
