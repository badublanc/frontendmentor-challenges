<svelte:head>
	<title>Badu's QR Code</title>
</svelte:head>

<main class="min-h-screen flex items-center justify-center">
	<div
		id="container"
		class="flex flex-col items-center bg-white outfit pt-4 rounded-3xl space-y-4 drop-shadow-xl"
	>
		<img src="/assets/qr-code.png" alt="qr code" id="code" class="rounded-xl" />
		<h1 class="w-4/5 text-center heading-text pt-2">
			Improve your front-end skills by building projects
		</h1>
		<p class="w-4/5 text text-center">
			Scan the QR code to visit Frontend Mentor and take you coding skills to the next level
		</p>
	</div>
</main>

<style>
	/* 
	- White: hsl(0, 0%, 100%)
	- Light gray: hsl(212, 45%, 89%)
	- Grayish blue: hsl(220, 15%, 55%)
	- Dark blue: hsl(218, 44%, 22%)
	*/
	@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@400;700&display=swap');

	main {
		background-color: hsl(212, 45%, 89%);
	}

	#container {
		width: 320px;
		height: 496px;
	}

	#code {
		width: 288px;
		height: 288px;
	}

	.outfit {
		font-family: 'Outfit', sans-serif;
	}

	.heading-text {
		font-size: 22px;
		line-height: 1.75rem;
		font-weight: 700;
		color: hsl(218, 44%, 22%);
	}

	.text {
		font-size: 15px;
		line-height: 1.15rem;
		font-weight: 400;
		color: hsl(220, 15%, 55%);
	}
</style>
