<script lang="ts">
	import './layout.css';
	import Logo from '$lib/assets/img/firey_83c.png';
	import { page } from '$app/state';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={Logo} />
	<title>thefirey33's fun stuff.</title>
</svelte:head>

<nav class="flex w-screen border-b border-gray-500 p-4 tracking-widest select-none md:text-3xl">
	<div class="mr-auto ml-auto flex flex-col items-center">
		<h1>thefirey33's fun stuff.</h1>
		<p class="bg-red-500 p-2 text-xs">attention: everything here is a parody.</p>
	</div>
</nav>

<div class="mr-auto ml-auto max-w-300 p-5">
	{#if page.url.pathname != '/'}
		<button class="btn text-xl" onclick={() => history.back()}>go back</button>{/if}
	{@render children()}
</div>
