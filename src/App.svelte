<script>
	import { fade } from 'svelte/transition';
	let name = '...';
	let checked;
	$: isMark = name.toUpperCase() === 'MARK';

</script>

<div class="greeter">
	<h1 class="greeter__h1"  >Hello <span class:highlight={isMark}>{name}</span>!</h1>
	<p class="paragraph greeter__p">Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

	<input 
		type="text" 
		class="greeter__input" 
		bind:value={name}
	/>
	<input 
		type="checkbox"
		class="greeter__input greeter__checkbox" 
		bind:checked
	/>

	{#if checked}
		<div transition:fade={{duration: 300}} class="checked-box">now you see me</div>
	{/if}

</div>

<style>
	.greeter {
		text-align: center;
		padding: 1em;
		max-width: 60vw;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.highlight {
		color: blue;
	}

</style>