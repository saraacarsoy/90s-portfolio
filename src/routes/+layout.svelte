<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<div class="app">
	<main>
		{@render children()}
	</main>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		font-size: 2rem;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 3rem 3rem;
		width: 100%;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>
