<script>
	export let name;

	let rando = 0;
	let count = 0;
	let direction = 0;
	$: count = count + direction*rando;

	function setRando() {
		direction = Math.random() < 0.5 ? -1 : 1;
		rando = Math.floor(Math.random()*100);
	}

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}!</h1>
<p>this is the random number {rando}</p>
<p>so the total is <b>{count}<b></p>
<p>the direction is {direction}</p>
<hr>
<button on:click={setRando}>Randomize</button>
<hr>
{#if count > 75}
	<p>Show 😎</p>
{:else if count > 50 }
	<p>Tá beleza 😛</p>
{:else}
	<p>É o jeito 😔</p>
{/if}
