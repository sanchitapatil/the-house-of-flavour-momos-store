<script>
	let activeTab = $state('steam'); 
	let activeMood = $state('all'); // 'all', 'juicy', 'cheesy', 'savory'
	let selectedIngredient = $state(null); // To show custom ingredient tooltips

	const tabs = [
		{ id: 'steam', label: 'STEAMED', desc: 'Juicy & Classic', icon: '💨' },
		{ id: 'kurkure', label: 'KURKURE', desc: 'Crispy & Crunchy', icon: '🔥' },
		{ id: 'periperi', label: 'PERI-PERI', desc: 'Spicy & Fiery', icon: '🌶️' }
	];

	const moods = [
		{ id: 'all', label: 'Show All 🥟', desc: 'Browse full menu' },
		{ id: 'juicy', label: 'Classic & Juicy 🥬', desc: 'Match Veg Momos', target: 'veg' },
		{ id: 'cheesy', label: 'Cheesy Melt 🧀', desc: 'Match Cheese Corn', target: 'cheese' },
		{ id: 'savory', label: 'Rich & Savory 🧈', desc: 'Match Paneer Momos', target: 'paneer' }
	];

	const menuItems = [
		{
			id: 'veg',
			mood: 'juicy',
			name: "Signature Veg Momos",
			ingredients: [
				{ name: "Ginger", icon: "🧄", note: "Freshly ground for a warm, sharp kick." },
				{ name: "Garlic", icon: "🧄", note: "Crushed daily to infuse aromatic flavor." },
				{ name: "Cabbage", icon: "🥬", note: "Hand-shredded local cabbage for peak crunch." },
				{ name: "Capsicum", icon: "🫑", note: "Diced fresh green capsicum." },
				{ name: "Onion", icon: "🧅", note: "Sweet red onions finely chopped." },
				{ name: "Carrot", icon: "🥕", note: "Grated sweet red carrots." }
			],
			prices: { steam: 70, kurkure: 90, periperi: 100 },
			desc: "Thin-wrapped flat momos packed with seasoned fresh garden vegetables."
		},
		{
			id: 'cheese',
			mood: 'cheesy',
			name: "Cheese Corn Momos",
			ingredients: [
				{ name: "Sweet Corn", icon: "🌽", note: "Golden kernels popping with sweetness." },
				{ name: "Cheddar", icon: "🧀", note: "Sharp cheddar for a savory punch." },
				{ name: "Mozzarella", icon: "🧀", note: "Gooey mozzarella for the ultimate cheese pull." },
				{ name: "Garlic", icon: "🧄", note: "Infused garlic butter essence." },
				{ name: "Onion", icon: "🧅", note: "Sweet chopped red onions." }
			],
			prices: { steam: 120, kurkure: 140, periperi: 150 },
			desc: "A melting, gooey center of premium cheeses mixed with golden sweet corn."
		},
		{
			id: 'paneer',
			mood: 'savory',
			name: "Rich Paneer Momos",
			ingredients: [
				{ name: "Amul Paneer", icon: "🧈", note: "Creamy, fresh Amul paneer crumbled daily." },
				{ name: "Ginger", icon: "🧄", note: "Zesty fresh ginger notes." },
				{ name: "Garlic", icon: "🧄", note: "Ground local garlic paste." },
				{ name: "Cabbage", icon: "🥬", note: "Fine shredded cabbage wrapper." },
				{ name: "Spring Onion", icon: "🧅", note: "Chopped green spring onions." }
			],
			prices: { steam: 110, kurkure: 130, periperi: 140 },
			desc: "Stuffed with rich, grated Amul paneer and aromatic ground herbs."
		}
	];

	function selectMood(m) {
		activeMood = m;
	}

	function toggleIngredient(ingName) {
		if (selectedIngredient === ingName) {
			selectedIngredient = null;
		} else {
			selectedIngredient = ingName;
		}
	}
</script>

<section class="py-24 px-6 bg-hof-charcoal relative" id="menu">
	<!-- Chalk dust overlay -->
	<div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0IiBoZWlnaHQ9IjQiPjxyZWN0IHdpZHRoPSI0IiBoZWlnaHQ9IjQiIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iMC4wMSIvPjwvc3ZnPg==')] opacity-15 pointer-events-none"></div>

	<div class="max-w-6xl mx-auto relative z-10">
		
		<!-- Section Title Section -->
		<div class="text-center mb-16">
			<span class="text-hof-yellow font-[var(--font-heading)] tracking-widest text-sm uppercase">CHOOSE YOUR FLAVOUR</span>
			<h2 class="font-[var(--font-heading)] text-5xl md:text-6xl text-white mt-2 chalk-glow-white rotate-[-0.5deg]">
				The Menu Board
			</h2>
			<span class="block font-[var(--font-doodle)] text-hof-red text-3xl mt-2 rotate-[1deg]">
				Steamed, Crispy or Fiery Spiced!
			</span>
			<svg class="w-48 h-4 mx-auto text-hof-red mt-4 opacity-80" viewBox="0 0 200 20" preserveAspectRatio="none">
				<path d="M0,10 Q25,18 50,10 T100,10 T150,10 T200,10" fill="none" stroke="currentColor" stroke-width="3" />
			</svg>
		</div>

		<!-- Interactive Mood Matcher Banner (Highly Engaging Quiz) -->
		<div class="bg-hof-slate p-6 rounded-3xl border border-neutral-850 mb-16 text-center max-w-4xl mx-auto">
			<h3 class="font-[var(--font-heading)] text-lg text-white mb-4 tracking-wider">
				❓ WHAT'S YOUR VIBE TODAY?
			</h3>
			<div class="flex flex-wrap justify-center gap-3">
				{#each moods as mood}
					<button 
						class="px-5 py-2.5 rounded-xl border font-body text-xs font-semibold tracking-wider transition-all duration-300 cursor-pointer
						{activeMood === mood.id 
							? 'bg-hof-yellow text-hof-black border-hof-yellow shadow-[0_4px_12px_rgba(241,196,15,0.2)] scale-102' 
							: 'bg-hof-black text-gray-400 border-neutral-800 hover:border-neutral-700 hover:text-white'}"
						onclick={() => selectMood(mood.id)}
					>
						{mood.label}
						<span class="block text-[9px] opacity-70 font-normal mt-0.5">{mood.desc}</span>
					</button>
				{/each}
			</div>
		</div>

		<!-- Preparation Style Vector Board (Visual Chalkboard Representation) -->
		<div class="bg-hof-slate rounded-3xl border border-neutral-850 p-8 mb-16 max-w-4xl mx-auto flex flex-col md:flex-row items-center gap-8 relative overflow-hidden">
			<!-- Chalk Graphic Column -->
			<div class="w-full md:w-1/3 flex justify-center relative">
				<div class="w-32 h-32 rounded-2xl bg-hof-black border-2 border-dashed border-neutral-700 flex items-center justify-center relative overflow-hidden select-none">
					{#if activeTab === 'steam'}
						<!-- Animated Steam Vector -->
						<svg class="w-20 h-20 text-white/80 animate-pulse" viewBox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="3">
							<path d="M30 70 C30 50, 45 40, 50 20 C55 40, 70 50, 70 70 Z" />
							<path d="M40 80 Q 50 60 40 40" stroke-dasharray="3 3" />
							<path d="M60 80 Q 50 60 60 40" stroke-dasharray="3 3" />
						</svg>
					{:else if activeTab === 'kurkure'}
						<!-- Crispy Sparks Vector -->
						<svg class="w-20 h-20 text-hof-yellow animate-float" viewBox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="3">
							<path d="M50 15 L55 35 L75 40 L55 45 L50 65 L45 45 L25 40 L45 35 Z" fill="rgba(241,196,15,0.1)" />
							<circle cx="50" cy="40" r="2" fill="currentColor" />
							<line x1="15" y1="15" x2="25" y2="25" />
							<line x1="85" y1="15" x2="75" y2="25" />
						</svg>
					{:else}
						<!-- Fiery Chili Flame Vector -->
						<svg class="w-20 h-20 text-hof-red animate-pulse" viewBox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="3">
							<path d="M50 15 C30 30, 20 60, 40 80 C60 90, 80 70, 70 40 C65 60, 55 65, 50 15 Z" fill="rgba(231,76,60,0.1)"/>
						</svg>
					{/if}
				</div>
			</div>
			
			<!-- Chalk Text Details Column -->
			<div class="w-full md:w-2/3 text-center md:text-left flex flex-col justify-center">
				<span class="text-xs font-bold text-neutral-500 uppercase tracking-widest">Active Prep Style</span>
				<h3 class="font-[var(--font-heading)] text-3xl text-white mt-1 uppercase tracking-wide">
					{tabs.find(t => t.id === activeTab).label} PREPARATION
				</h3>
				<p class="text-gray-400 font-light text-sm mt-3 leading-relaxed">
					{#if activeTab === 'steam'}
						Piping hot momos steamed slowly inside a professional stainless steel steamer to the perfect time, exactly when you order. Thin skins remain soft, locking in all natural vegetable juices for a light, classic, and healthy bite.
					{:else if activeTab === 'kurkure'}
						Coated in a crunchy, spiced cornflake batter and deep-fried to a golden crisp. Offers a massive crunch on the outside while remaining tender and hot on the inside.
					{:else}
						Fried to a light crisp and tossed instantly in our hot, savory Peri-Peri seasoning dust. Spicy, tangy, and packed with an energetic punch.
					{/if}
				</p>
			</div>
		</div>

		<!-- Menu Style Switcher (Interactive Tabs) -->
		<div class="flex flex-col sm:flex-row justify-center gap-4 mb-16">
			{#each tabs as tab}
				<button 
					class="flex-1 px-8 py-4 font-[var(--font-heading)] text-lg border-2 transition-all duration-300 rounded-xl cursor-pointer
					{activeTab === tab.id 
						? 'bg-hof-yellow text-hof-black border-hof-yellow shadow-[0_5px_15px_rgba(241,196,15,0.2)]' 
						: 'bg-transparent border-neutral-800 text-gray-400 hover:border-neutral-700 hover:text-white'}"
					onclick={() => activeTab = tab.id}
				>
					{tab.label} {tab.icon}
				</button>
			{/each}
		</div>

		<!-- Menu Card Grid -->
		<div class="grid grid-cols-1 md:grid-cols-3 gap-10">
			{#each menuItems as item}
				<!-- Card wrapper checks if it matches activeMood for highlight -->
				<div 
					class="group bg-hof-slate rounded-3xl border transition-all duration-500 p-8 flex flex-col justify-between shadow-2xl relative overflow-visible min-h-[380px]
					{activeMood === item.mood 
						? 'border-hof-yellow scale-[1.03] shadow-[0_8px_30px_rgba(241,196,15,0.15)] bg-neutral-900/50' 
						: 'border-neutral-850 opacity-90'}"
				>
					<!-- Top banner for mood matched selection -->
					{#if activeMood === item.mood}
						<div class="absolute -top-3 left-6 bg-hof-yellow text-hof-black font-[var(--font-heading)] text-[10px] px-3 py-1 rounded-full border border-white tracking-wider animate-bounce select-none">
							🎯 YOUR MATCH!
						</div>
					{/if}

					<!-- Price Tag Bubble -->
					<div class="absolute -top-3 -right-3 bg-hof-red text-white font-[var(--font-heading)] text-2xl px-5 py-2.5 rounded-2xl rotate-[8deg] shadow-lg border border-white">
						₹{item.prices[activeTab]}
					</div>

					<div>
						<!-- Item Title -->
						<h3 class="font-[var(--font-heading)] text-2xl text-white mb-3 pr-12 group-hover:text-hof-yellow transition-colors tracking-wide">
							{item.name}
						</h3>
						
						<!-- Item Description -->
						<p class="text-xs text-gray-400 mb-6 font-light leading-relaxed">
							{item.desc}
						</p>

						<!-- Ingredients sketches (Interactive Toggle Details) -->
						<div class="mb-6">
							<span class="text-[10px] uppercase font-bold text-hof-green tracking-widest block mb-2">INGREDIENTS (TAP TO EXPLORE)</span>
							<div class="flex flex-wrap gap-2">
								{#each item.ingredients as ingredient}
									<button 
										class="font-body text-xs px-2.5 py-1 rounded-lg border flex items-center gap-1.5 cursor-pointer transition-all duration-300
										{selectedIngredient === ingredient.name 
											? 'bg-hof-yellow text-hof-black border-hof-yellow shadow-md' 
											: 'bg-hof-black text-gray-300 border-neutral-850 hover:border-neutral-700'}"
										onclick={() => toggleIngredient(ingredient.name)}
									>
										<span>{ingredient.icon}</span>
										<span>{ingredient.name}</span>
									</button>
								{/each}
							</div>
						</div>
					</div>

					<!-- Bottom card details: Dynamic interactive ingredient info panel -->
					<div class="pt-4 border-t border-dashed border-neutral-850 mt-auto">
						{#if selectedIngredient}
							<!-- Find matched ingredient notes -->
							{@const selectedIngObj = item.ingredients.find(i => i.name === selectedIngredient)}
							{#if selectedIngObj}
								<div class="bg-hof-black/60 p-3 rounded-xl border border-neutral-800 text-[11px] text-hof-yellow font-body font-light animate-pulse">
									<strong class="font-bold block text-white uppercase mb-1">
										{selectedIngObj.icon} {selectedIngObj.name} Notes:
									</strong>
									"{selectedIngObj.note}"
								</div>
							{/if}
						{:else}
							<div class="flex justify-between items-center text-xs font-bold text-neutral-500 uppercase">
								<span>Portion Size</span>
								<span class="text-white">6 Pieces</span>
							</div>
						{/if}
					</div>
				</div>
			{/each}
		</div>

		<!-- Footer details -->
		<div class="mt-16 text-center max-w-2xl mx-auto bg-hof-slate p-6 rounded-2xl border border-neutral-800">
			<p class="text-sm text-gray-400">
				* All plates consist of <span class="text-hof-yellow font-bold">6 pieces</span> of freshly hand-folded momos. Served along with signature <span class="text-hof-red font-bold">Chilli Charm Chutney</span> and mayo at our cart.
			</p>
		</div>

	</div>
</section>
