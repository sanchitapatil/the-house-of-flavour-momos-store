<script>
	import { Code, Users, Award, Heart } from '@lucide/svelte';
</script>

<section class="py-24 px-6 bg-hof-charcoal relative overflow-hidden" id="story">
	<!-- Subtle background pattern -->
	<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0IiBoZWlnaHQ9IjQiPjxyZWN0IHdpZHRoPSI0IiBoZWlnaHQ9IjQiIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4wMSIvPjwvc3ZnPg==')] opacity-20 pointer-events-none"></div>

	<div class="max-w-5xl mx-auto relative z-10">
		<!-- Header -->
		<div class="text-center mb-16">
			<span class="text-hof-yellow font-[var(--font-heading)] tracking-widest text-sm uppercase">OUR STORY</span>
			<h2 class="font-[var(--font-heading)] text-5xl md:text-6xl text-white mt-2 chalk-glow-white rotate-[-0.5deg]">
				From IT to the Food Cart
			</h2>
			<span class="block font-[var(--font-doodle)] text-hof-red text-3xl mt-2 rotate-[1.5deg]">
				Our Journey 🖤
			</span>
			<svg class="w-48 h-4 mx-auto text-hof-red mt-4 opacity-80" viewBox="0 0 200 20" preserveAspectRatio="none">
				<path d="M 10,10 Q 100,18 190,10 Q 100,2 10,10" fill="none" stroke="currentColor" stroke-width="3" />
			</svg>
		</div>

		<!-- Story Timeline Card Layout -->
		<div class="space-y-12">
			
			<!-- Stage 1 -->
			<div class="group bg-hof-slate p-8 rounded-3xl border border-neutral-850 hover:border-hof-yellow/30 transition-all duration-300 grid grid-cols-1 md:grid-cols-12 gap-8 items-start relative">
				<div class="md:col-span-1 flex justify-center">
					<div class="w-12 h-12 bg-hof-yellow/10 rounded-2xl flex items-center justify-center border border-hof-yellow/20 text-hof-yellow">
						<Code size={20} />
					</div>
				</div>
				<div class="md:col-span-11">
					<h3 class="font-[var(--font-heading)] text-2xl text-white tracking-wide mb-3 flex flex-wrap items-center gap-2">
						The Spark: <span class="text-hof-yellow">From IT to the Steamer</span> 💻✨
					</h3>
					<p class="text-gray-400 font-light leading-relaxed text-sm md:text-base">
						For years, my world was filled with code, screens, and the fast-paced life of an IT professional. But my heart? It was always in the kitchen. Cooking wasn't just a hobby; it was my love language. In 2025, during the Ganpati festival, I decided to step away from the keyboard and do something just for fun—I set up a small, temporary momo stall. I just wanted to share my love for pure, authentic, homemade comfort food with our community.
					</p>
				</div>
			</div>

			<!-- Stage 2 -->
			<div class="group bg-hof-slate p-8 rounded-3xl border border-neutral-850 hover:border-hof-green/30 transition-all duration-300 grid grid-cols-1 md:grid-cols-12 gap-8 items-start relative">
				<div class="md:col-span-1 flex justify-center">
					<div class="w-12 h-12 bg-hof-green/10 rounded-2xl flex items-center justify-center border border-hof-green/20 text-hof-green">
						<Users size={20} />
					</div>
				</div>
				<div class="md:col-span-11">
					<h3 class="font-[var(--font-heading)] text-2xl text-white tracking-wide mb-3 flex flex-wrap items-center gap-2">
						The Turning Point: <span class="text-hof-green">6,000+ Momos & Empowering Women</span> 👩‍🍳🚀
					</h3>
					<p class="text-gray-400 font-light leading-relaxed text-sm md:text-base">
						What started as a festive experiment turned into an absolute whirlwind of love. The response was overwhelming. People didn't just eat the momos; they kept coming back for more, completely hooked on our thin-wrapped, juicy flat momos and the fiery punch of our signature Chilli Charm Chutney.
					</p>
					<p class="text-gray-400 font-light leading-relaxed text-sm md:text-base mt-4">
						As demand skyrocketed, I realized this was bigger than just a hobby. I made the leap to turn my passion into a purpose. To keep up with the love while maintaining our strict "made from scratch daily" quality, I brought on a team of four incredible women. Together, crafting everything in small batches with big love, we rolled, stuffed, and served over 6,000+ momos!
					</p>
				</div>
			</div>

			<!-- Stage 3 -->
			<div class="group bg-hof-slate p-8 rounded-3xl border border-neutral-850 hover:border-hof-red/30 transition-all duration-300 grid grid-cols-1 md:grid-cols-12 gap-8 items-start relative">
				<div class="md:col-span-1 flex justify-center">
					<div class="w-12 h-12 bg-hof-red/10 rounded-2xl flex items-center justify-center border border-hof-red/20 text-hof-red">
						<Award size={20} />
					</div>
				</div>
				<div class="md:col-span-11">
					<h3 class="font-[var(--font-heading)] text-2xl text-white tracking-wide mb-3 flex flex-wrap items-center gap-2">
						Today: <span class="text-hof-red">House of Flavour</span> 🏮
					</h3>
					<p class="text-gray-400 font-light leading-relaxed text-sm md:text-base">
						That wave of community support and shared joy is what brought us here today. We officially transitioned from a temporary stall to our very own dedicated street food cart: <span class="font-bold text-white">House of Flavour</span>.
					</p>
					<p class="text-gray-400 font-light leading-relaxed text-sm md:text-base mt-4">
						We don't use shortcuts, and we never compromise on ingredients. Every plate of Veg, Cheese Corn, or Paneer momos we serve is a testament to that original festival joy—fresh, honest, and packed with a <span class="text-hof-yellow font-bold">Flavour That Speaks</span>.
					</p>
				</div>
			</div>

		</div>
	</div>
</section>
