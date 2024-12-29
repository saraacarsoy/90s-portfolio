<script lang="ts">
	import File from './File.svelte';
</script>

<svelte:head>
	<title>Sara Nil Acarsoy Portfolio</title>
	<meta name="description" content="Sara Nil Acarsoy Portfolio" />
</svelte:head>

<section>

</section>

<aside>
	<File name={"About"}/>
	<File name={"Contact"}/>
</aside>

<style>
	aside {
		display: flex;
		flex-direction: column;
		gap: 30px;
		width: fit-content;
	}
</style>
