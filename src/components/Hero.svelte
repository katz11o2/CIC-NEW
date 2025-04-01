<script>
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import { goto } from '$app/navigation';


	// Stats data
	const stats = [
		{ label: 'Industry Partners', value: '50+', prefix: '' },
		{ label: 'Patents Filed', value: '30+', prefix: '' },
		{ label: 'Success Rate', value: '95', prefix: '%' }
	];

	// News ticker data
	const news = [
		'Student Startups Raised $5M+ This Quarter',
		'Cambridge Institute named Top Innovation Hub 2024',
		'New Industry Partnership Program Launched',
		'Student Startups Raised $5M+ This Quarter',
		'Join Our Next Innovation Workshop',
		'Cambridge Institute named Top Innovation Hub 2024',
	];

	let currentNewsIndex = 0;
	let isVisible = false;

	// News ticker animation
	onMount(() => {
		isVisible = true;
		const interval = setInterval(() => {
			currentNewsIndex = (currentNewsIndex + 1) % news.length;
		}, 4000);

		return () => clearInterval(interval);
	});

	// Featured opportunities
	const opportunities = [
		{
			title: 'Industry Innovation',
			description: 'Transform your business challenges into opportunities',
			cta: 'Submit Challenge',
			icon: '🎯'
		},
		{
			title: 'Research Partnership',
			description: 'Access cutting-edge research and development facilities',
			cta: 'Partner With Us',
			icon: '🔬'
		}
	];
</script>

<div class="relative min-h-screen w-full ">

	<!-- Main Content -->
	<main class="relative w-full px-0 pt-18">
		<div class="grid gap-12 w-full lg:grid-cols-2 lg:gap-24 bg-gradient-to-br from-slate-900 via-blue-500/40 to-slate-800 ">
			<!-- Left Column -->
			{#if isVisible}
				<div class="space-y-12" in:fly={{ y: 50, duration: 3000 }}>
					<!--	 Hero Text -->
					<div class="space-y-6">
						<h1 class="text-4xl leading-tight font-bold text-white lg:text-6xl xl:text-7xl">
							Industry Academia 
							
							<span class="bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent">
								Smart Initiative
							</span>
						
						</h1>
						<p class="max-w-xl text-lg text-blue-100/90 lg:text-xl">
							Join forces with Cambridge Institute's Innovation Center to pioneer breakthrough
							solutions that shape the future of industry and technology.
						</p>
					</div>

					<!-- CTA Section -->
					<div class="flex flex-wrap gap-6">
						<button 
	class="group relative inline-flex items-center gap-2 rounded-lg bg-blue-500 px-8 py-3.5 font-semibold text-white transition-all hover:bg-blue-600"
	on:click={() => goto('/loginforstudents')}
>
	Get Started
	<svg class="h-5 w-5 transition-transform group-hover:translate-x-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
		<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
	</svg>
	<div class="absolute -top-1 -right-1 flex h-3 w-3">
		<span class="absolute inline-flex h-full w-full animate-ping rounded-full bg-blue-400 opacity-75"></span>
		<span class="relative inline-flex h-3 w-3 rounded-full bg-blue-500"></span>
	</div>
</button>

<button 
class="inline-flex items-center gap-2 rounded-lg border border-blue-400/30 px-8 py-3.5 font-semibold text-blue-100 backdrop-blur-sm transition-all hover:bg-blue-400/10"
on:click={() => goto('/about')}
>
Learn More
</button>
					</div>

					<!-- Stats -->
					<div class="grid grid-cols-1 gap-6 sm:grid-cols-3">
						{#each stats as { label, value, prefix }}
							<div class="group rounded-xl bg-white/5 p-6 backdrop-blur-sm transition-all hover:bg-white/10">
								<p class="text-3xl font-bold text-white">{value}{prefix}</p>
								<p class="mt-2 text-sm text-blue-200">{label}</p>
							</div>
						{/each}
					</div>
				</div>
			{/if}

			<!-- Right Column -->
			{#if isVisible}
				<div class="relative space-y-8 lg:mt-12" in:fly={{ x: 80, duration: 3000 }}>
					<!-- Opportunity Cards -->
					<div class="relative space-y-6">
						{#each opportunities as { title, description, cta, icon }}
							<div class="group relative overflow-hidden rounded-xl border border-white/10 bg-white/5 p-8 backdrop-blur-sm transition-all hover:-translate-y-1 hover:bg-white/10">
								<div class="mb-4 text-3xl">{icon}</div>
								<h3 class="text-2xl font-semibold text-white">{title}</h3>
								<p class="mt-3 text-lg text-blue-200">{description}</p>
								<button class="mt-6 flex items-center text-sm font-medium text-blue-400 transition-all group-hover:text-blue-300">
									{cta}
									<svg class="ml-2 h-4 w-4 transition-transform group-hover:translate-x-1" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
										<path d="M7 17L17 7M17 7H7M17 7V17"/>
									</svg>
								</button>
							</div>
						{/each}
					</div>
				</div>
			{/if}
		</div>
	</main>
</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}

	
	h1{
		font-size: 4rem;
		position: relative;
		top: 10px;
		left:10px;
	}

	p{
		
		position: relative;
		top: 10px;
		left:10px;
	}

	button {	
		position: relative;
		top: 10px;
		left:10px;
	}

	

	

	.group {
        padding: 2 rem; /* Reduce padding for smaller box size */
        transition: all 0.6s ease;
    }

   

    .group .text-3xl {
        font-size: 1rem; /* Reduce the icon size to make the box look smaller */
    }

    .group .text-2xl {
        font-size: 1rem; /* Reduce title font size */
    }

    .group .text-lg {
        font-size: 1rem; /* Adjust text size for smaller boxes */
    }

	.grid {
		max-height: 1000px;
	}

	main {
		max-height: 2000px;
	}
</style>
