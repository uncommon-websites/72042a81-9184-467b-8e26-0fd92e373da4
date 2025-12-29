<script lang="ts">
	// Icons
	const icons = {
		logo: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-500"><path d="M12 2L14.5 9H22L16 13.5L18.5 21L12 16.5L5.5 21L8 13.5L2 9H9.5L12 2Z" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg>`, // Placeholder for flower
		clock: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
		arrowRight: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>`,
		reflection: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
		productivity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`,
		memory: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/><path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/></svg>`,
		clarity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 2v4"/><path d="M12 18v4"/><path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/><path d="M2 12h4"/><path d="M18 12h4"/><path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/></svg>`,
		speedometer: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M22 12A10 10 0 0 0 12 2v10z"/></svg>`, // Simplified
		shield: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`,
		sparkles: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>`,
		soundwave: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 2v20"/><path d="M16 6v12"/><path d="M20 10v4"/><path d="M8 6v12"/><path d="M4 10v4"/></svg>`,
		plus: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>`,
		check: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="20 6 9 17 4 12"/></svg>`,
		calendar: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
		repeat: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>`,
		search: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>`,
		camera: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>`,
		mic: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
		download: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`,
		layout: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
		target: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`,
		list: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>`,
		link: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>`,
		maximize: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>`,
		externalLink: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>`,
	};
</script>

<div class="min-h-screen bg-white">
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-4 max-w-7xl mx-auto">
		<div class="flex items-center gap-2">
			<!-- Logo Icon -->
			<div class="text-gray-900">
				<svg width="24" height="24" viewBox="0 0 97 93" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
					<path d="M57.1677 72.0913C49.5314 69.2599 41.6772 68.8244 34.4772 70.7844C29.459 72.0913 24.6592 74.7049 20.2956 77.9719L17.2411 80.5855L16.3684 81.4566L18.332 83.1991C18.5502 83.1991 18.5502 83.4169 18.7684 83.6347C19.2047 84.0702 19.6411 84.288 20.2956 84.7236L21.6047 85.5947L22.9137 84.5058C23.1319 84.288 23.5683 83.8524 24.0046 83.6347C27.9319 80.3677 32.2953 78.1897 36.8772 77.1008C42.768 75.576 49.0951 75.7938 55.4222 78.1897C60.6585 80.1499 71.3493 82.5455 84.2217 77.1008L84.6581 76.8827L85.3128 76.2294C85.3128 76.0116 85.5309 76.0116 85.7491 75.7938C86.8399 74.4871 87.9309 73.1802 88.8036 71.6557L93.167 64.9038L86.1854 68.8241C75.9309 74.4869 66.5493 75.576 57.1677 72.0913Z" fill="currentColor"/>
					<path d="M27.2782 48.5694C33.169 47.0449 39.4961 47.2627 45.8235 49.6585C52.8051 52.2721 70.6957 55.9746 90.7681 37.8974L95.1317 33.5413L94.6952 32.4524C94.477 31.5812 94.0407 30.4921 93.6044 29.4032L92.5136 26.354L90.3317 28.5318C90.1136 28.9676 89.6773 29.1854 89.2407 29.621C79.641 39.4218 64.8049 49.4407 47.7869 43.3424C40.1509 40.511 32.2964 40.0752 25.0964 42.0355C18.1148 43.9957 12.0058 47.6982 6.33317 52.9255V52.7077L3.0605 56.1924C3.0605 56.4102 2.84236 56.4102 2.62418 56.628L1.9696 57.2813L2.1878 58.1527C2.40597 59.2416 2.84232 60.3305 3.0605 61.4197L4.36959 64.9044L6.55135 62.073C6.76954 61.6374 7.20588 61.4197 7.42407 60.9841C12.0058 56.8458 18.333 50.9652 27.2782 48.5694Z" fill="currentColor"/>
					<path d="M6.11498 44.6486C11.1331 39.4214 16.8057 36.1544 22.9147 34.4119C28.8055 32.8874 35.1327 33.1052 41.4598 35.5011C61.0959 42.6883 78.1138 30.9272 85.5317 24.611L88.368 21.7796L89.4591 20.9085L88.5862 19.6016C87.9317 18.9482 87.4954 18.0771 86.8409 17.2057L85.5317 15.4635L84.0046 16.988C83.7864 17.2058 83.3501 17.6413 83.1317 17.8593C73.9683 26.5713 59.7867 35.5011 43.6416 29.4027C36.0053 26.5713 28.1511 26.1355 20.9511 28.0958C16.3693 29.4027 12.0058 31.5805 7.6422 34.4119L3.06044 38.1147C2.62409 38.5502 2.40591 38.768 1.96955 39.2036L1.53324 39.6391V40.2925C1.31506 41.8172 1.31503 43.3417 1.09685 44.6486L0.878662 50.0936L4.58772 46.1731C5.02406 45.7375 5.46045 45.0841 6.11498 44.6486Z" fill="currentColor"/>
				</svg>
			</div>
			<span class="font-bold text-xl tracking-tight">Fractal</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#" class="text-gray-600 hover:text-gray-900">Learn More</a>
			<a href="#" class="bg-gray-100 px-4 py-2 rounded-lg text-gray-900 hover:bg-gray-200 transition-colors">Sign In</a>
		</nav>
	</header>

	<main>
		<!-- Hero Section -->
		<section class="max-w-4xl mx-auto px-6 pt-12 pb-20 text-center">
			<div class="inline-flex items-center gap-2 text-gray-500 text-sm mb-6">
				{@html icons.sparkles}
				<span>Personal Cognitive Topology Platform</span>
			</div>
			
			<h1 class="text-5xl md:text-6xl font-bold tracking-tight text-gray-900 mb-6 leading-[1.1]">
				See the structure of your thinking
			</h1>
			
			<p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
				Transform journals, voice notes, and transcripts into a living visual map of concepts, relationships, and belief loops—without prescription.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto mb-16">
				<div class="relative w-full">
					<input 
						type="email" 
						placeholder="Your email address" 
						class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary-500/20 focus:border-primary-500 transition-all"
					/>
					<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-gray-600">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-xs text-left text-gray-500 w-full sm:w-auto shrink-0">
					Join the waitlist for<br>early access to Fractal.
				</div>
			</div>

			<!-- Visual Topology Representation -->
			<div class="relative rounded-2xl border border-gray-200 shadow-2xl bg-white overflow-hidden aspect-[16/10] mb-12 group">
				<!-- Network visualization concept -->
				<div class="absolute inset-0 bg-gradient-to-br from-gray-50 to-white flex items-center justify-center p-8">
					<!-- Central node network -->
					<div class="relative w-full h-full max-w-2xl max-h-96">
						<!-- Connection lines -->
						<svg class="absolute inset-0 w-full h-full" viewBox="0 0 400 300">
							<line x1="200" y1="150" x2="100" y2="80" stroke="currentColor" stroke-width="1" class="text-gray-300" />
							<line x1="200" y1="150" x2="300" y2="80" stroke="currentColor" stroke-width="1" class="text-gray-300" />
							<line x1="200" y1="150" x2="320" y2="200" stroke="currentColor" stroke-width="1" class="text-gray-300" />
							<line x1="200" y1="150" x2="80" y2="220" stroke="currentColor" stroke-width="1" class="text-gray-300" />
							<line x1="100" y1="80" x2="300" y2="80" stroke="currentColor" stroke-width="1" class="text-gray-200" />
							<line x1="80" y1="220" x2="320" y2="200" stroke="currentColor" stroke-width="1" class="text-gray-200" />
						</svg>
						
						<!-- Nodes -->
						<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-16 h-16 rounded-full bg-primary-500 flex items-center justify-center text-white text-xs font-bold shadow-lg">
							Self
						</div>
						<div class="absolute top-[27%] left-1/4 w-12 h-12 rounded-full bg-gray-800 flex items-center justify-center text-white text-xs shadow-md">
							Work
						</div>
						<div class="absolute top-[27%] right-1/4 w-12 h-12 rounded-full bg-gray-700 flex items-center justify-center text-white text-xs shadow-md">
							Fear
						</div>
						<div class="absolute bottom-[33%] right-[20%] w-10 h-10 rounded-full bg-gray-600 flex items-center justify-center text-white text-xs shadow-md">
							Time
						</div>
						<div class="absolute bottom-[27%] left-[20%] w-10 h-10 rounded-full bg-gray-500 flex items-center justify-center text-white text-xs shadow-md">
							Rest
						</div>
					</div>
				</div>
				
				<!-- Overlay text -->
				<div class="absolute inset-0 flex items-center justify-center bg-black/5 opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none">
					<span class="bg-white px-4 py-2 rounded-full shadow-sm text-sm font-medium">Your Cognitive Map</span>
				</div>
			</div>

			<!-- Bottom Icons -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-12 text-sm font-medium text-gray-700">
				<div class="flex items-center gap-2">
					{@html icons.reflection}
					<span>For self-reflection</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.memory}
					<span>For understanding</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.clarity}
					<span>For clarity</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.sparkles}
					<span>For insight</span>
				</div>
			</div>
		</section>

		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-2xl leading-tight">
				Your thoughts have structure. Fractal makes it visible.
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.layout}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Visual topology</h3>
						<p class="text-sm text-gray-600 leading-relaxed">See concepts, relationships, and patterns emerge as living visual maps</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.repeat}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Belief loops</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Discover recurring patterns and circular thinking in your mental models</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.shield}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">No prescription</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Understand your thinking without being told what to believe or do</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.mic}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Multiple inputs</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Journals, voice notes, and transcripts all feed your cognitive map</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.sparkles}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Living structure</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Your map evolves as you add new reflections and insights</p>
					</div>
				</div>

				<!-- Card 6 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.clarity}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Inner freedom</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Gain clarity and self-understanding without dogma or coaching</p>
					</div>
				</div>
			</div>
		</section>

		<!-- Visual Mapping Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Cognitive Topology
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Watch your thinking take shape
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Fractal transforms your reflections into visual maps that reveal patterns, connections, and belief loops you never knew existed.
				</p>
			</div>

			<div class="bg-gray-50 rounded-3xl p-8 md:p-12 mb-16">
				<!-- Visual Concept Map Example -->
				<div class="bg-white rounded-2xl shadow-lg p-8 md:p-12 mb-8">
					<div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
						<!-- Left: Journal Entry -->
						<div class="space-y-4">
							<div class="text-xs text-gray-400 mb-4">Journal Entry · March 15</div>
							<div class="prose prose-sm text-gray-700 leading-relaxed">
								<p class="mb-3">I keep saying I don't have time for creative work, but I spent three hours scrolling today. The truth is I'm afraid of starting because I might not be good enough.</p>
								<p class="mb-3">This reminds me of how I felt before launching my first project—paralyzed by perfectionism. Maybe the pattern isn't about time at all.</p>
								<p>What if the real block is fear of judgment, not lack of hours?</p>
							</div>
						</div>

						<!-- Right: Emerging Map -->
						<div class="relative h-80 bg-gradient-to-br from-gray-50 to-white rounded-xl border border-gray-200 p-6">
							<div class="text-xs text-gray-400 mb-4">Emerging Patterns</div>
							<!-- Simple node visualization -->
							<svg class="w-full h-full" viewBox="0 0 300 250">
								<!-- Connections -->
								<line x1="150" y1="125" x2="80" y2="60" stroke="currentColor" stroke-width="1.5" class="text-gray-300" />
								<line x1="150" y1="125" x2="220" y2="60" stroke="currentColor" stroke-width="1.5" class="text-gray-300" />
								<line x1="150" y1="125" x2="150" y2="200" stroke="currentColor" stroke-width="2" class="text-primary-400" />
								<line x1="80" y1="60" x2="220" y2="60" stroke="currentColor" stroke-width="1" class="text-gray-200" />
								
								<!-- Nodes -->
								<g>
									<circle cx="150" cy="125" r="28" fill="currentColor" class="text-primary-500" />
									<text x="150" y="130" text-anchor="middle" class="text-xs fill-white font-medium">Fear</text>
								</g>
								<g>
									<circle cx="80" cy="60" r="22" fill="currentColor" class="text-gray-700" />
									<text x="80" y="64" text-anchor="middle" class="text-xs fill-white font-medium">Time</text>
								</g>
								<g>
									<circle cx="220" cy="60" r="22" fill="currentColor" class="text-gray-600" />
									<text x="220" y="64" text-anchor="middle" class="text-xs fill-white font-medium">Creative</text>
								</g>
								<g>
									<circle cx="150" cy="200" r="24" fill="currentColor" class="text-gray-800" />
									<text x="150" y="204" text-anchor="middle" class="text-xs fill-white font-medium">Judgment</text>
								</g>
							</svg>
							<div class="absolute bottom-4 left-4 text-xs text-gray-500 bg-white px-2 py-1 rounded border border-gray-200">
								Belief loop detected
							</div>
						</div>
					</div>
				</div>

			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-6 max-w-4xl">
				<p class="text-xl text-gray-600 mb-6 md:col-span-2 leading-relaxed">
					Every entry you add enriches your cognitive map. Fractal reveals the invisible architecture of your thinking—the concepts you return to, the connections you make, and the loops that shape your worldview.
				</p>
				
				<div class="space-y-4">
					<div class="flex items-center gap-3 text-gray-700 font-medium">
						{@html icons.layout}
						<span>Concept relationships</span>
					</div>
					<div class="flex items-center gap-3 text-gray-700 font-medium">
						{@html icons.repeat}
						<span>Recurring patterns</span>
					</div>
					<div class="flex items-center gap-3 text-gray-700 font-medium">
						{@html icons.link}
						<span>Belief structures</span>
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center gap-3 text-gray-700 font-medium">
						{@html icons.search}
						<span>Hidden assumptions</span>
					</div>
					<div class="flex items-center gap-3 text-gray-700 font-medium">
						{@html icons.target}
						<span>Core themes</span>
					</div>
					<div class="flex items-center gap-3 text-gray-700 font-medium">
						{@html icons.sparkles}
						<span>Emergent insights</span>
					</div>
				</div>
			</div>
		</section>

		<!-- Understanding Patterns Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Self-Understanding
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Understand yourself, without judgment
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Fractal doesn't tell you what to think or do. It simply shows you the structure of your own mind—revealing patterns, loops, and connections you can explore on your terms.
				</p>
			</div>

			<div class="bg-gray-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
					<!-- Pattern Card 1 -->
					<div class="bg-white rounded-xl p-6 shadow-sm">
						<div class="w-12 h-12 rounded-full bg-primary-100 flex items-center justify-center mb-4">
							{@html icons.repeat}
						</div>
						<h3 class="font-bold text-gray-900 mb-2">Recurring Themes</h3>
						<p class="text-sm text-gray-600 leading-relaxed">
							See which concepts appear most frequently in your reflections and how they connect to other ideas.
						</p>
					</div>

					<!-- Pattern Card 2 -->
					<div class="bg-white rounded-xl p-6 shadow-sm">
						<div class="w-12 h-12 rounded-full bg-primary-100 flex items-center justify-center mb-4">
							{@html icons.link}
						</div>
						<h3 class="font-bold text-gray-900 mb-2">Belief Loops</h3>
						<p class="text-sm text-gray-600 leading-relaxed">
							Discover circular patterns in your thinking—where one belief reinforces another in an ongoing cycle.
						</p>
					</div>

					<!-- Pattern Card 3 -->
					<div class="bg-white rounded-xl p-6 shadow-sm">
						<div class="w-12 h-12 rounded-full bg-primary-100 flex items-center justify-center mb-4">
							{@html icons.sparkles}
						</div>
						<h3 class="font-bold text-gray-900 mb-2">Emergent Insights</h3>
						<p class="text-sm text-gray-600 leading-relaxed">
							Watch new connections form as your map grows, revealing insights that weren't visible before.
						</p>
					</div>
				</div>
			</div>

			<div class="max-w-3xl mx-auto text-center">
				<p class="text-xl text-gray-600 leading-relaxed mb-8">
					Fractal is a mirror, not a guide. It reflects your thinking back to you with clarity, helping you see patterns you might have missed—but it never prescribes what those patterns should mean or what you should do about them.
				</p>
				<p class="text-lg text-gray-500 italic">
					"The unexamined life is not worth living, but the over-examined life is not worth living either."
				</p>
			</div>
		</section>

		<!-- Image Section -->
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
				<div>
					<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-6 leading-tight">
						Your inner world, made visible
					</h2>
					<p class="text-lg text-gray-600 mb-6 leading-relaxed">
						Fractal is for those who seek to understand themselves more deeply—not through external validation or prescribed paths, but through the quiet work of self-reflection and pattern recognition.
					</p>
					<p class="text-lg text-gray-600 leading-relaxed">
						Join a community of deep thinkers who are exploring the topology of their own minds.
					</p>
				</div>
				<div class="relative rounded-2xl overflow-hidden shadow-2xl">
					<img 
						src="/generated/image-person-in-meditation-or-deep-thought-by--1767051882023-2.webp" 
						alt="Person in contemplation by window" 
						class="w-full h-auto"
					/>
				</div>
			</div>
		</section>

		<!-- Who uses it Section -->
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					For Deep Thinkers
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Who is Fractal for?
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Writers, thinkers, creators, therapists, and contemplative practitioners who want to understand the structure of their thinking without dogma or prescription.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
				<!-- Card 1 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Writers</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Explore the themes and patterns that emerge across your work, revealing your unique creative voice.</p>
				</div>
				<!-- Card 2 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Therapists</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Map client narratives and belief structures to support deeper therapeutic insight.</p>
				</div>
				<!-- Card 3 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Contemplatives</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Track your spiritual journey and see how your understanding evolves over time.</p>
				</div>
				<!-- Card 4 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Researchers</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Visualize connections between ideas and discover new angles in your research.</p>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Creators</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Understand the conceptual foundations of your creative practice and identify new directions.</p>
				</div>
				<!-- Card 6 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Philosophers</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Map your philosophical inquiries and see how your arguments and beliefs interconnect.</p>
				</div>
				<!-- Card 7 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Journalers</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Transform daily reflections into a visual map of your personal growth and evolution.</p>
				</div>
				<!-- Card 8 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Seekers</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Navigate your path of self-discovery with clarity, seeing patterns emerge without prescription.</p>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-12 border-t border-gray-100">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Resources</h4>
					<div class="grid grid-cols-2 gap-x-8 gap-y-3 text-xs text-gray-600">
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.reflection} Understanding cognitive topology
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.sparkles} Getting started with Fractal
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.layout} Exploring belief loops
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.clarity} Deep reflection practices
						</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center mt-12 pt-8 text-xs text-gray-400">
				<div class="flex items-center gap-2 mb-4 md:mb-0">
					<div class="w-6 h-6 text-gray-300">
						<svg width="24" height="24" viewBox="0 0 97 93" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
							<path d="M57.1677 72.0913C49.5314 69.2599 41.6772 68.8244 34.4772 70.7844C29.459 72.0913 24.6592 74.7049 20.2956 77.9719L17.2411 80.5855L16.3684 81.4566L18.332 83.1991C18.5502 83.1991 18.5502 83.4169 18.7684 83.6347C19.2047 84.0702 19.6411 84.288 20.2956 84.7236L21.6047 85.5947L22.9137 84.5058C23.1319 84.288 23.5683 83.8524 24.0046 83.6347C27.9319 80.3677 32.2953 78.1897 36.8772 77.1008C42.768 75.576 49.0951 75.7938 55.4222 78.1897C60.6585 80.1499 71.3493 82.5455 84.2217 77.1008L84.6581 76.8827L85.3128 76.2294C85.3128 76.0116 85.5309 76.0116 85.7491 75.7938C86.8399 74.4871 87.9309 73.1802 88.8036 71.6557L93.167 64.9038L86.1854 68.8241C75.9309 74.4869 66.5493 75.576 57.1677 72.0913Z" fill="currentColor"/>
							<path d="M27.2782 48.5694C33.169 47.0449 39.4961 47.2627 45.8235 49.6585C52.8051 52.2721 70.6957 55.9746 90.7681 37.8974L95.1317 33.5413L94.6952 32.4524C94.477 31.5812 94.0407 30.4921 93.6044 29.4032L92.5136 26.354L90.3317 28.5318C90.1136 28.9676 89.6773 29.1854 89.2407 29.621C79.641 39.4218 64.8049 49.4407 47.7869 43.3424C40.1509 40.511 32.2964 40.0752 25.0964 42.0355C18.1148 43.9957 12.0058 47.6982 6.33317 52.9255V52.7077L3.0605 56.1924C3.0605 56.4102 2.84236 56.4102 2.62418 56.628L1.9696 57.2813L2.1878 58.1527C2.40597 59.2416 2.84232 60.3305 3.0605 61.4197L4.36959 64.9044L6.55135 62.073C6.76954 61.6374 7.20588 61.4197 7.42407 60.9841C12.0058 56.8458 18.333 50.9652 27.2782 48.5694Z" fill="currentColor"/>
							<path d="M6.11498 44.6486C11.1331 39.4214 16.8057 36.1544 22.9147 34.4119C28.8055 32.8874 35.1327 33.1052 41.4598 35.5011C61.0959 42.6883 78.1138 30.9272 85.5317 24.611L88.368 21.7796L89.4591 20.9085L88.5862 19.6016C87.9317 18.9482 87.4954 18.0771 86.8409 17.2057L85.5317 15.4635L84.0046 16.988C83.7864 17.2058 83.3501 17.6413 83.1317 17.8593C73.9683 26.5713 59.7867 35.5011 43.6416 29.4027C36.0053 26.5713 28.1511 26.1355 20.9511 28.0958C16.3693 29.4027 12.0058 31.5805 7.6422 34.4119L3.06044 38.1147C2.62409 38.5502 2.40591 38.768 1.96955 39.2036L1.53324 39.6391V40.2925C1.31506 41.8172 1.31503 43.3417 1.09685 44.6486L0.878662 50.0936L4.58772 46.1731C5.02406 45.7375 5.46045 45.0841 6.11498 44.6486Z" fill="currentColor"/>
						</svg>
					</div>
					<div>
						<p>Copyright © 2025 Fractal</p>
						<p>All rights reserved. Terms of Service & Privacy Policy.</p>
					</div>
				</div>
				<div class="bg-gray-200 text-gray-600 px-3 py-1 rounded text-xs font-medium">
					Status
				</div>
			</div>
		</footer>

	</main>
</div>

