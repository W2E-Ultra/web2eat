<script lang="ts">
	let clicked = false
	let hue = Math.floor(Math.random() * 360)
	const clicker = () => {
		clicked = !clicked
	} 
</script>

<title>ẘḧɇŗɵ ʈƍ ⱷɒⱡ</title>
<main style={`--hue: ${hue}`}>
	{#if !clicked}
		<button
			id="shake"
			on:click={() => clicker()}
			on:focus={() => {hue = Math.floor(Math.random() * 360)}}
			on:mouseover={() => {hue = Math.floor(Math.random() * 360)}}
		>
			摇
		</button>
	{/if}
	
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	#shake {
		margin-top: 20vh;
		transition: 1s cubic-bezier(0, 1.5, 0, 1);
		width: 20em;
		height: 14em;
		background: whitesmoke;
	}

	#shake:hover {
		transform: skew(-20deg);
		background: hsl(var(--hue), 80%, 65%);
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>