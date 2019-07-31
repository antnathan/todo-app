<script>
	export let name;

	import { randomStore } from './store';

	import Child from './Child.svelte';

	let data = {
		userName: "Nathan",
		userId: 12398471,
		userEmail: 'ant.nathan@email.com'
	}

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<div>
	{ $randomStore }	
</div>
<hr/>
<button on:click={() => randomStore.set(Math.random())}> Set</button>

<Child {...data}/>