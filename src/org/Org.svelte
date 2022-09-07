<script>
	export let name = 'Organisasjon';
	const secret = process.env.SECRET
</script>

<div>
	<h2>{name}!</h2>
	<p>Yes yes dette er orgen vår {secret} </p>
</div>

<style>
	h1 {
		color: var(--deepSeaGreen);
	}

</style>