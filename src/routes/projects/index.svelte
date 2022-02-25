<script>
	import { onMount } from 'svelte';

	let name = 'Jonathan';

	onMount(async () => {
		// do something on mount

		return () => {
			// do something on destroy
		};
	});
</script>

<div>
	<h1>Hi, {name}</h1>
</div>
