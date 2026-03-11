<script lang="ts">
	import './layout.css';
	import Logo from '$lib/assets/img/firey_83c.png';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={Logo} />
	<title>thefirey33's fun stuff.</title>
</svelte:head>

<div
	class="flex min-h-20 w-screen justify-center border-b border-gray-500 p-4 tracking-widest select-none md:text-3xl"
>
	<div class="flex flex-col items-center">
		<h1>thefirey33's fun stuff.</h1>
		<h1 class="text-xl">for funsies.</h1>
	</div>
</div>

<div class="mr-auto ml-auto max-w-300 p-5">
	{@render children()}
</div>
