<script>
	import Scene from './Scene.svelte';
	import { Canvas } from '@threlte/core';
	import { ArrowRight, Flame, MapPin, Phone } from '@lucide/svelte';
</script>

<!-- Navigation Header -->
<header class="absolute top-0 inset-x-0 z-50 flex items-center justify-between px-6 py-6 max-w-7xl mx-auto pointer-events-auto">
	<div class="flex items-center gap-4">
		<div class="w-16 h-16 bg-white rounded-full flex items-center justify-center p-1.5 shadow-md">
			<img src="/images/hof logo.png" alt="House of Flavour Logo" class="w-full h-full object-contain" />
		</div>
		<span class="font-[var(--font-heading)] text-2xl text-white tracking-wider hidden sm:inline">HOUSE OF FLAVOUR</span>
	</div>
	
	<nav class="hidden md:flex items-center gap-8 font-body text-sm font-semibold tracking-wider text-gray-400">
		<a href="#menu" class="hover:text-hof-yellow transition-colors">THE MENU</a>
		<a href="#about" class="hover:text-hof-yellow transition-colors">OUR PROMISE</a>
		<a href="#chutney" class="hover:text-hof-yellow transition-colors">CHUTNEY SPOTLIGHT</a>
		<a href="#location" class="hover:text-hof-yellow transition-colors">FIND US</a>
	</nav>
	
	<div>
		<a href="tel:7666480844" class="inline-flex items-center gap-2 bg-hof-black border border-neutral-800 hover:border-hof-green px-5 py-2.5 rounded-full font-body text-xs font-bold tracking-widest text-white transition-colors">
			<Phone size={14} class="text-hof-green" />
			<span>CALL</span>
		</a>
	</div>
</header>

<section class="relative min-h-screen flex items-center justify-center overflow-hidden px-6 py-32 md:py-20 bg-hof-black">
	<!-- Canvas Background Layer -->
	<div class="absolute inset-0 z-0 pointer-events-none opacity-40 lg:opacity-65">
		<Canvas>
			<Scene />
		</Canvas>
	</div>

	<!-- Scribbly layout overlays -->
	<div class="absolute inset-0 pointer-events-none z-10 overflow-hidden select-none">
		<!-- Huge backdrop text representing authentic street chalkboard writing -->
		<div class="absolute top-[20%] left-[-5%] text-neutral-900/40 font-[var(--font-heading)] text-[12vw] tracking-wider uppercase rotate-[-6deg]">
			MOMOS
		</div>
		<div class="absolute bottom-[10%] right-[-5%] text-neutral-900/40 font-[var(--font-heading)] text-[12vw] tracking-wider uppercase rotate-[4deg]">
			CHUTNEY
		</div>

		<!-- Sketched chalk circle highlight around the main headline -->
		<svg class="absolute top-[18%] left-[2%] w-[96%] h-[60%] text-hof-yellow/5 opacity-40" viewBox="0 0 1000 600" preserveAspectRatio="none">
			<path d="M 50,300 C 50,150 950,100 950,300 C 950,500 50,450 50,300" fill="none" stroke="currentColor" stroke-width="8" stroke-dasharray="15 15" />
		</svg>
	</div>

	<div class="relative z-20 max-w-7xl mx-auto w-full grid grid-cols-1 lg:grid-cols-12 gap-16 items-center">
		<!-- Left side: Bold expressive typography -->
		<div class="lg:col-span-7 flex flex-col items-center lg:items-start text-center lg:text-left">
			<!-- Chalk doodle tag -->
			<div class="inline-flex items-center gap-2 bg-gradient-to-r from-hof-red to-hof-yellow text-hof-black font-[var(--font-heading)] text-sm px-6 py-2 rounded-full rotate-[-2deg] shadow-lg mb-8 tracking-wider">
				<Flame size={16} fill="currentColor" />
				<span>100% PURE VEGETARIAN HOMEMADE</span>
			</div>

			<!-- Core Title with layered neon shadows -->
			<h1 class="font-[var(--font-heading)] text-6xl sm:text-7xl md:text-8xl lg:text-9xl text-white leading-[1.05] tracking-wide mb-6 uppercase rotate-[-1deg] chalk-glow-white select-none">
				Flavour <br />
				<span class="text-hof-yellow chalk-glow-yellow">That Speaks</span>
			</h1>

			<!-- Doodle tagline -->
			<div class="font-[var(--font-doodle)] text-hof-green text-3xl sm:text-4xl lg:text-5xl mb-8 rotate-[1.5deg] tracking-wide select-none">
				"Pure comfort in every single bite! 🧄🧅🥟"
			</div>

			<!-- Headline details -->
			<p class="font-body text-base sm:text-lg lg:text-xl text-gray-400 mb-10 max-w-xl font-light leading-relaxed select-none">
				Crafted fresh daily in small batches using premium veggies. Served hot with our signature, fiery <span class="text-hof-red font-semibold underline decoration-wavy decoration-hof-red/80">Chilli Charm Garlic Chutney</span>.
			</p>

			<!-- CTAs styled like chalkboard banners -->
			<div class="flex flex-col sm:flex-row gap-6 w-full sm:w-auto relative">
				<a href="#location" class="group relative inline-flex items-center justify-center bg-hof-yellow text-hof-black font-[var(--font-heading)] text-xl py-4 px-10 rounded-xl transition-all shadow-[0_8px_20px_rgba(241,196,15,0.3)] hover:scale-105 active:scale-95 border-2 border-white">
					Find Our Cart
					<ArrowRight size={18} class="ml-2 group-hover:translate-x-1 transition-transform" />
				</a>

				<a href="#menu" class="group relative inline-flex items-center justify-center bg-transparent text-white font-[var(--font-heading)] text-xl py-4 px-10 rounded-xl transition-all border-2 border-neutral-700 hover:border-white hover:scale-105 active:scale-95">
					View Menu
				</a>

				<!-- Curly arrow doodle decoration pointing to Menu -->
				<svg class="hidden xl:block absolute -left-24 top-6 w-20 h-20 text-hof-red rotate-12" viewBox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="2">
					<path d="M10 20 Q 30 10 50 30 Q 70 50 65 75" />
					<path d="M50 70 L 65 75 L 70 60" />
					<text x="5" y="55" fill="currentColor" class="font-[var(--font-doodle)] text-xl">Spicy!</text>
				</svg>
			</div>
		</div>

		<!-- Right side: Beautiful high-contrast visual display -->
		<div class="lg:col-span-5 flex justify-center relative w-full mt-12 lg:mt-0">
			<!-- Visual background neon glow -->
			<div class="absolute w-[80%] h-[80%] bg-gradient-to-tr from-hof-red via-hof-yellow to-hof-green opacity-10 rounded-full blur-3xl -z-10 animate-pulse"></div>

			<!-- Floating rotating stamp -->
			<div class="absolute -top-12 -left-12 w-36 h-36 bg-hof-charcoal border-2 border-dashed border-hof-yellow rounded-full flex flex-col items-center justify-center rotate-[-12deg] z-30 shadow-2xl animate-spin-slow select-none p-2">
				<span class="font-[var(--font-heading)] text-center text-[10px] text-white tracking-wider leading-none mb-1">BEST PURE VEG</span>
				<span class="font-[var(--font-heading)] text-center text-xl text-hof-yellow tracking-widest leading-none">MOMOS</span>
				<span class="font-[var(--font-doodle)] text-center text-sm text-hof-green leading-none mt-1">in Wakad, Pune</span>
			</div>

			<!-- Premium Poster / Blackboard display panel -->
			<div class="relative bg-hof-slate p-5 rounded-3xl border border-neutral-800 shadow-2xl rotate-2 transition-transform duration-500 hover:rotate-0 w-full max-w-md">
				<!-- Top frame details -->
				<div class="flex justify-between items-center mb-4 px-2 select-none">
					<span class="text-xs font-bold tracking-widest text-neutral-500 uppercase">STEAMING FRESH DAILY</span>
					<span class="text-xs font-bold tracking-widest text-hof-red animate-pulse">● LIVE STEAMING</span>
				</div>

				<div class="overflow-hidden rounded-2xl border border-neutral-800 relative bg-hof-black">
					<img src="/images/momos.png" alt="Steaming Momos and Chutney" class="w-full h-auto object-cover transform transition-transform duration-700 hover:scale-105" />
					
					<!-- Floating label inside photo -->
					<div class="absolute bottom-4 left-4 bg-hof-black/80 backdrop-blur-md px-4 py-2 rounded-lg border border-neutral-800">
						<p class="font-[var(--font-doodle)] text-xl text-white">"Tastes just like home..."</p>
					</div>
				</div>

				<!-- Blackboard chalk writeups at footer of image -->
				<div class="mt-5 flex justify-between items-center px-1">
					<div class="flex flex-col">
						<span class="font-[var(--font-heading)] text-lg text-white">HOUSE OF FLAVOUR</span>
						<span class="font-body text-xs text-neutral-500">Premium Veg Momos & Chutney</span>
					</div>
					<div class="bg-hof-black px-4 py-2 rounded-lg border border-neutral-800 rotate-[-2deg]">
						<span class="font-[var(--font-doodle)] text-xl text-hof-yellow">Freshly Steamed!</span>
					</div>
				</div>
			</div>

			<!-- Chalk steam doodle vector overlay -->
			<svg class="absolute -top-16 right-10 w-24 h-24 text-white/10 pointer-events-none" viewBox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="2">
				<path d="M30 80 Q 20 60 30 40 T 20 10" />
				<path d="M50 80 Q 40 60 50 40 T 40 10" />
				<path d="M70 80 Q 60 60 70 40 T 60 10" />
			</svg>
		</div>
	</div>
</section>
