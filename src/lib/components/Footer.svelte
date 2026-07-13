<script>
	import { MapPin, Phone, Navigation } from '@lucide/svelte';
</script>

<footer class="bg-hof-charcoal py-20 border-t-8 border-hof-yellow relative overflow-hidden" id="location">
	<!-- Chalk dust overlay -->
	<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0IiBoZWlnaHQ9IjQiPjxyZWN0IHdpZHRoPSI0IiBoZWlnaHQ9IjQiIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4wMiIvPjwvc3ZnPg==')] opacity-20 pointer-events-none"></div>

	<div class="max-w-6xl mx-auto px-6 grid grid-cols-1 md:grid-cols-3 gap-16 relative z-10">
		
		<!-- HOF Brand Details -->
		<div class="flex flex-col items-center md:items-start text-center md:text-left select-none">
			<div class="flex items-center gap-3 mb-3">
				<div class="w-16 h-16 bg-white rounded-full flex items-center justify-center p-1.5 shadow-md">
					<img src="/images/hof logo.png" alt="House of Flavour Logo" class="w-full h-full object-contain" />
				</div>
				<span class="font-[var(--font-heading)] text-2xl text-white tracking-wider">HOUSE OF FLAVOUR</span>
			</div>
			<p class="font-[var(--font-doodle)] text-2xl text-hof-red mb-8 rotate-[2deg]">
				Flavour that speaks!
			</p>
			
			<div class="space-y-4 w-full">
				<!-- Phone link structured like a blackboard list item -->
				<a href="tel:7666480844" class="inline-flex items-center gap-3 bg-hof-black hover:bg-neutral-900 border-2 border-dashed border-neutral-700 hover:border-hof-green p-4 rounded-xl transition-all w-full max-w-sm justify-center md:justify-start group">
					<Phone size={24} class="text-hof-green group-hover:scale-110 transition-transform" />
					<div>
						<span class="text-xs uppercase text-neutral-500 font-bold block text-left">Call Us</span>
						<span class="font-[var(--font-heading)] text-xl text-white">76664 80844</span>
					</div>
				</a>

				<!-- WhatsApp link structured like a blackboard list item -->
				<a href="https://wa.me/917666480844?text=Hello!%20I'd%20like%20to%20connect%20with%20House%20of%20Flavour." target="_blank" class="inline-flex items-center gap-3 bg-hof-black hover:bg-neutral-900 border-2 border-dashed border-neutral-700 hover:border-hof-green p-4 rounded-xl transition-all w-full max-w-sm justify-center md:justify-start group">
					<svg class="w-6 h-6 text-hof-green group-hover:scale-110 transition-transform" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
						<path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L0 24l6.335-1.662c1.746.953 3.71 1.458 5.704 1.459h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413" fill="currentColor"/>
					</svg>
					<div>
						<span class="text-xs uppercase text-neutral-500 font-bold block text-left">WhatsApp Us</span>
						<span class="font-[var(--font-heading)] text-xl text-white">76664 80844</span>
					</div>
				</a>
				
				<!-- Instagram link with custom SVG icon -->
				<a href="https://instagram.com/houseofflavour_momos" target="_blank" class="inline-flex items-center gap-3 bg-hof-black hover:bg-neutral-900 border-2 border-dashed border-neutral-700 hover:border-hof-red p-4 rounded-xl transition-all w-full max-w-sm justify-center md:justify-start group">
					<svg class="w-6 h-6 text-hof-red group-hover:scale-110 transition-transform" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<rect width="20" height="20" x="2" y="2" rx="5" ry="5"/>
						<path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/>
						<line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/>
					</svg>
					<div>
						<span class="text-xs uppercase text-neutral-500 font-bold block text-left">Follow the Flavour</span>
						<span class="font-body text-base text-gray-300">@houseofflavour_momos</span>
					</div>
				</a>
			</div>
		</div>

		<!-- Cart Location Details -->
		<div class="flex flex-col items-center md:items-start text-center md:text-left">
			<h3 class="font-[var(--font-heading)] text-2xl text-white mb-6 chalk-text-white flex items-center gap-2">
				<MapPin class="text-hof-yellow" /> Cart Location
			</h3>
			
			<div class="bg-hof-black p-6 rounded-2xl border-2 border-neutral-800 rotate-[1deg] mb-8 w-full max-w-sm">
				<h4 class="font-[var(--font-heading)] text-xl text-hof-yellow mb-2">Wakad Branch</h4>
				<p class="text-gray-400 font-light leading-relaxed text-sm">
					Our street cart is parked and serving hot, steamy, fresh momos daily. Drop by for authentic street vibes!
				</p>
			</div>
			
			<a href="https://maps.app.goo.gl/iwYw2siURFxRdDAKA" target="_blank" class="w-full max-w-sm inline-flex justify-center items-center gap-2 bg-white text-hof-black font-[var(--font-heading)] text-lg py-4 px-8 rough-border hover:bg-neutral-200 transition-colors shadow-lg">
				<Navigation size={18} />
				Navigate on Maps
			</a>
		</div>

		<!-- Operating Hours chalkboard board -->
		<div class="flex flex-col items-center md:items-start text-center md:text-left">
			<h3 class="font-[var(--font-heading)] text-2xl text-white mb-6 chalk-text-white">
				Opening Hours
			</h3>
			
			<div class="w-full max-w-sm bg-hof-black p-8 rough-border-yellow rotate-[-1deg] text-center flex flex-col justify-center items-center min-h-[200px]">
				<span class="font-[var(--font-heading)] text-2xl text-white mb-2">6 PM - 10 PM</span>
				<span class="font-[var(--font-doodle)] text-3xl text-hof-green rotate-[2deg] mb-4">Daily Fresh!</span>
				<span class="text-xs uppercase text-hof-red font-bold block border-t border-dashed border-neutral-800 pt-4 w-full">
					Thursday Closed
				</span>
			</div>
		</div>

	</div>
	
	<div class="mt-20 pt-8 border-t border-neutral-900 text-center text-neutral-600 text-sm select-none">
		&copy; {new Date().getFullYear()} House of Flavour. Hand-crafted with 🤍 & 🌶️
	</div>
</footer>
