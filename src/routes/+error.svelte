<script lang="ts">
	import { page } from '$app/state';
	import { onMount } from 'svelte';

	let shakePosition = $state({
		x: 0,
		y: 0
	});
	const shakeAmount = 3;

	function returnRandomNumber() {
		return Math.random() * shakeAmount - Math.random() * shakeAmount;
	}

	onMount(() => {
		let isActive = true;

		let doShakeFrame = () => {
			shakePosition = { x: returnRandomNumber(), y: returnRandomNumber() };
			if (isActive) requestAnimationFrame(doShakeFrame);
		};

		requestAnimationFrame(doShakeFrame);

		return () => {
			isActive = false;
		};
	});
</script>

<div class="m-auto flex flex-col items-center justify-center gap-4">
	<h1 class="text-3xl md:text-6xl">{page.status}.</h1>

	<!-- entire copypaste in here. -->
	<p class="md:text-xl" style="transform: translate({shakePosition.x}px, {shakePosition.y}px);">
		Connection terminated. I'm sorry to interrupt you, Elizabeth, if you still even remember that
		name, But I'm afraid you've been misinformed.
	</p>
</div>
