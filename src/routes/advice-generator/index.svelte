<script>
	let loading = false;
	let data = {
		id: 117,
		advice:
			"It is easy to sit up and take notice, what's difficult is getting up and taking action."
	};

	const getAdvice = async () => {
		loading = true;
		try {
			const response = await fetch('https://api.adviceslip.com/advice', { cache: 'no-cache' });
			const advice = await response.json();
			data = advice.slip;
			loading = false;
		} catch (error) {
			console.log(error);
		}
	};
</script>

<svelte:head>
	<title>Badu's Advice Generator</title>
</svelte:head>

<main class="min-h-screen page-bg flex flex-col items-center justify-center">
	<div
		class="dark-gray-bg flex flex-col space-y-6 max-w-xl items-center rounded-2xl px-10 md:px-12 pt-12 pb-16 manrope mx-6"
	>
		{#if loading}
			<img src="/assets/loading-2.gif" alt="" class="h-32 w-32 mb-3" />
		{:else}
			<h1 class="uppercase heading-text text-xs">advice #{data.id}</h1>
			<p class="quote-text text-center px-2 pb-2 leading-snug">"{data.advice}"</p>
		{/if}

		<img src="/assets/ag-divider-desktop.svg" alt="" class="pt-2" />
	</div>

	<button on:click={getAdvice} class="button-bg p-5 rounded-full -mt-8" aria-label="Refresh advice">
		<img src="/assets/ag-dice.svg" alt="" class="" />
	</button>
</main>

<style>
	/* Colors
		Light Cyan: hsl(193, 38%, 86%)
		Neon Green: hsl(150, 100%, 66%)
		Grayish Blue: hsl(217, 19%, 38%)
		Dark Grayish Blue: hsl(217, 19%, 24%)
	*/
	@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@700&display=swap');

	.button-bg {
		background-color: hsl(150, 100%, 66%);
	}

	.button-bg:hover {
		box-shadow: 0 0px 36px 0px hsl(150, 100%, 66%);
	}

	.page-bg {
		background-color: #202632;
	}

	.dark-gray-bg {
		background-color: hsl(217, 19%, 24%);
	}

	.manrope {
		font-family: 'Manrope', sans-serif;
	}

	.quote-text {
		color: hsl(193, 38%, 86%);
		font-size: 28px;
	}

	.heading-text {
		color: hsl(150, 100%, 66%);
		letter-spacing: 0.3em;
	}
</style>
