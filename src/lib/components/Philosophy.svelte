<script>
	import { Leaf, Flame, Heart } from '@lucide/svelte';
</script>

<section class="py-24 px-6 bg-hof-black border-y-4 border-neutral-900 relative overflow-hidden" id="about">
	<!-- Chalk dust overlay -->
	<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0IiBoZWlnaHQ9IjQiPjxyZWN0IHdpZHRoPSI0IiBoZWlnaHQ9IjQiIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4wMiIvPjwvc3ZnPg==')] opacity-30 pointer-events-none"></div>

	<div class="max-w-6xl mx-auto relative z-10">
		<!-- Section Header -->
		<div class="text-center mb-20 relative">
			<span class="text-hof-yellow font-[var(--font-heading)] tracking-widest text-sm uppercase">HOW WE DO IT</span>
			<h2 class="font-[var(--font-heading)] text-5xl md:text-6xl text-white tracking-wide mt-2 chalk-glow-white rotate-[-0.5deg]">
				The Promise
			</h2>
			<span class="block font-[var(--font-doodle)] text-hof-green text-3xl mt-2 rotate-[1.5deg]">
				Quality ingredients, clean kitchen, pure love.
			</span>
			<svg class="w-48 h-4 mx-auto text-hof-red mt-4 opacity-80" viewBox="0 0 200 20" preserveAspectRatio="none">
				<path d="M 10,10 Q 100,18 190,10 Q 100,2 10,10" fill="none" stroke="currentColor" stroke-width="3" />
			</svg>
		</div>

		<!-- Interactive Promises Grid -->
		<div class="grid grid-cols-1 md:grid-cols-3 gap-10">
			<!-- Promise 1 -->
			<div class="group bg-hof-slate p-8 rounded-3xl border border-neutral-800 hover:border-hof-yellow/50 transition-all duration-300 relative overflow-hidden flex flex-col items-center text-center">
				<!-- Top accent -->
				<div class="absolute inset-x-0 top-0 h-1.5 bg-hof-yellow"></div>
				
				<!-- Icon Container with glowing ring -->
				<div class="w-20 h-20 bg-hof-charcoal rounded-full border border-neutral-800 flex items-center justify-center mb-8 relative group-hover:scale-110 transition-transform">
					<div class="absolute inset-0 bg-hof-yellow/10 rounded-full blur-md"></div>
					<Flame size={36} class="text-hof-yellow" />
				</div>
				
				<h3 class="font-[var(--font-heading)] text-2xl text-white tracking-wider mb-4 group-hover:text-hof-yellow transition-colors">
					Freshly Prepared
				</h3>
				
				<p class="text-gray-400 font-light leading-relaxed text-sm">
					Made daily in small batches for peak freshness. No shortcuts, no leftovers. We steam and fry as you order.
				</p>
				
				<span class="font-[var(--font-doodle)] text-2xl text-hof-yellow mt-6 rotate-[-2deg]">
					"Prepared fresh daily!"
				</span>
			</div>

			<!-- Promise 2 -->
			<div class="group bg-hof-slate p-8 rounded-3xl border border-neutral-800 hover:border-hof-green/50 transition-all duration-300 relative overflow-hidden flex flex-col items-center text-center">
				<!-- Top accent -->
				<div class="absolute inset-x-0 top-0 h-1.5 bg-hof-green"></div>
				
				<!-- Icon Container with glowing ring -->
				<div class="w-20 h-20 bg-hof-charcoal rounded-full border border-neutral-800 flex items-center justify-center mb-8 relative group-hover:scale-110 transition-transform">
					<div class="absolute inset-0 bg-hof-green/10 rounded-full blur-md"></div>
					<Leaf size={36} class="text-hof-green" />
				</div>
				
				<h3 class="font-[var(--font-heading)] text-2xl text-white tracking-wider mb-4 group-hover:text-hof-green transition-colors">
					Pure Veg & Clean
				</h3>
				
				<p class="text-gray-400 font-light leading-relaxed text-sm">
					Prepared with high-quality ingredients and fried exclusively in refined sunflower oil inside a fully sanitised vegetarian kitchen.
				</p>
				
				<span class="font-[var(--font-doodle)] text-2xl text-hof-green mt-6 rotate-[2deg]">
					"100% Vegetarian!"
				</span>
			</div>

			<!-- Promise 3 -->
			<div class="group bg-hof-slate p-8 rounded-3xl border border-neutral-800 hover:border-hof-red/50 transition-all duration-300 relative overflow-hidden flex flex-col items-center text-center">
				<!-- Top accent -->
				<div class="absolute inset-x-0 top-0 h-1.5 bg-hof-red"></div>
				
				<!-- Icon Container with glowing ring -->
				<div class="w-20 h-20 bg-hof-charcoal rounded-full border border-neutral-800 flex items-center justify-center mb-8 relative group-hover:scale-110 transition-transform">
					<div class="absolute inset-0 bg-hof-red/10 rounded-full blur-md"></div>
					<Heart size={36} class="text-hof-red" />
				</div>
				
				<h3 class="font-[var(--font-heading)] text-2xl text-white tracking-wider mb-4 group-hover:text-hof-red transition-colors">
					Homemade Goodness
				</h3>
				
				<p class="text-gray-400 font-light leading-relaxed text-sm">
					No preservatives or MSG. Just authentic homemade recipe comfort food that warms you up inside out.
				</p>
				
				<span class="font-[var(--font-doodle)] text-2xl text-hof-red mt-6 rotate-[-1.5deg]">
					"Made with Love!"
				</span>
			</div>
		</div>
	</div>
</section>
