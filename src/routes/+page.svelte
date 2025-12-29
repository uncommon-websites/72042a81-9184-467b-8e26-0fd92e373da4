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
		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-lg leading-tight">
				Great ideas start in quiet places, welcome to your private think space.
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.speedometer}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Built for flow</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Fast, modern mobile and desktop apps that work offline</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.shield}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Private by design</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Stored on your device and syncs with end-to-end encryption</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.sparkles}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Works with AI</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Intelligent agents that think with you and organize your vault</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.soundwave}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Speak to journal</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Dictate your ideas and thoughts effortlessly</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.plus}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Capture effortlessly</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Text, links, photos, screenshots, and more</p>
					</div>
				</div>
			</div>
		</section>

		<!-- Think Tank Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-purple-100 text-purple-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					With best-in-class AI
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-purple-900 mb-6 tracking-tight">
					Your personal think tank
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Intelligent agents that organize and enhance your thinking. Your intellectual force multiplier.
				</p>
			</div>

			<div class="bg-purple-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
					<!-- Left Visual: Nova Agent -->
					<div class="relative bg-white rounded-2xl shadow-lg p-6 overflow-hidden min-h-[300px]">
						<div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-purple-500 to-pink-500"></div>
						<div class="flex items-center gap-3 mb-6">
							<div class="w-10 h-10 rounded-full bg-gradient-to-br from-purple-600 to-orange-400 flex items-center justify-center text-white font-bold text-xs">
								N
							</div>
							<div>
								<div class="font-bold text-gray-900">Nova</div>
								<div class="text-xs text-purple-600 font-medium uppercase tracking-wider">The Playful Explorer</div>
							</div>
						</div>
						<div class="space-y-4 text-sm">
							<div class="bg-purple-50 p-4 rounded-xl rounded-tl-none text-gray-800">
								I approach life like one big fascinating experiment, asking "what if" questions that make people see things in completely new ways. I believe play and humor are powerful tools for breaking through mental barriers.
							</div>
							<div class="flex gap-2">
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Extraverted</span>
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Intuitive</span>
							</div>
							<div class="flex gap-2">
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Thinking</span>
								<span class="bg-purple-900 text-white px-3 py-1 rounded-full text-xs font-medium">Perceiving</span>
							</div>
						</div>
						<div class="mt-6">
							<button class="w-full py-2 border border-purple-200 text-purple-700 font-medium rounded-lg hover:bg-purple-50 transition-colors">
								Add to vault
							</button>
						</div>
					</div>

					<!-- Right Visual: Chat Interface -->
					<div class="bg-white rounded-2xl shadow-lg p-6 min-h-[300px] flex flex-col">
						<div class="flex items-center gap-2 mb-4 text-xs text-gray-400 border-b border-gray-100 pb-2 overflow-hidden whitespace-nowrap">
							<div class="w-2 h-2 rounded-full bg-gray-300"></div>
							<span>https://nabeelqu.substack.com/p/reflections-on-palantir</span>
						</div>
						<div class="flex-1 space-y-4">
							<div class="border border-gray-100 rounded-lg p-4">
								<h4 class="font-bold text-gray-900 text-sm mb-1">Reflections on Palantir</h4>
								<div class="text-xs text-gray-500 mb-2">nabeelqu.substack.com</div>
								<p class="text-xs text-gray-600 line-clamp-3">
									Chronos shares five on-site stories—from mapping Afghan IEDs to fixing Airbus delays—that show Palantir teams hacking bespoke fixes, then baking them into reusable Foundry modules.
								</p>
							</div>
							<div class="flex gap-2 items-center text-xs text-gray-500">
								<div class="flex -space-x-2">
									<div class="w-6 h-6 rounded-full bg-gray-200 border-2 border-white"></div>
									<div class="w-6 h-6 rounded-full bg-gray-300 border-2 border-white"></div>
								</div>
								<span>Lens and Chronos</span>
							</div>
							<div class="space-y-3 pt-2">
								<div class="flex gap-3">
									<div class="w-6 h-6 rounded-full bg-gray-800 shrink-0"></div>
									<div class="text-xs text-gray-800">
										<p class="font-bold mb-1">tell me everything about rene descartes</p>
									</div>
								</div>
								<div class="flex gap-3">
									<div class="w-6 h-6 rounded-full bg-teal-500 shrink-0"></div>
									<div class="text-xs text-gray-600 bg-gray-50 p-3 rounded-lg rounded-tl-none">
										<p>AI for physical action: doubt filter, cogito reset, clarify rewrite, first-principles ladder, axis plotting, mind-body separation.</p>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Bottom Visual: Input Processing -->
				<div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
					<div class="relative mb-8">
						<input type="text" value="What are you thinking?" class="w-full bg-gray-50 border-none rounded-xl py-4 pl-12 pr-4 text-gray-500 focus:ring-0" readonly />
						<div class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400">
							{@html icons.camera}
						</div>
						<div class="absolute right-4 top-1/2 -translate-y-1/2 flex gap-2 text-gray-400">
							{@html icons.mic}
							{@html icons.download}
						</div>
					</div>

					<div class="flex justify-center mb-8">
						<span class="bg-gray-100 text-gray-500 text-xs px-3 py-1 rounded-full">gpt-5 is out! should we switch you to it?</span>
					</div>

					<div class="bg-purple-50/50 rounded-xl p-6 border border-purple-100">
						<div class="space-y-3">
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-pink-500 animate-pulse"></div>
								<span class="text-sm text-gray-700">Nova is working</span>
							</div>
							<div class="flex items-start gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500 mt-1"></div>
								<div class="text-sm text-gray-700">
									<span class="font-medium">Nova is scanning</span> 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">132 recent entries</span> 
									to understand your context and checking 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">8 lists</span> 
									for relevant topics.
									<p class="text-xs text-gray-500 mt-1 max-w-md">Found mentions of ChatGPT in your vault for additional context. Distill is using AI to analyze patterns and suggest relevant connections.</p>
								</div>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500"></div>
								<span class="text-sm text-gray-700">Added entry to <span class="bg-purple-500 text-white px-2 py-0.5 rounded text-xs font-bold">ideas</span></span>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full border-2 border-gray-300 border-t-gray-500 animate-spin"></div>
								<span class="text-sm text-gray-500">Searching the web for <span class="text-blue-500">openai gpt-5</span></span>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-4 max-w-4xl">
				<p class="text-xl text-gray-600 mb-6 md:col-span-2 leading-relaxed">
					They watch your threads, spot patterns, and do the groundwork you don't have time for—mapping connections, organizing lists, and surfacing the right context on cue.
				</p>
				
				<div class="space-y-4">
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.sparkles}
						<span>Agents engage with you</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.target}
						<span>Guide you towards your goals</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.plus}
						<span>Auto-organize entries into lists</span>
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.layout}
						<span>Connect the dots across threads</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.maximize}
						<span>Read and summarize links</span>
					</div>
					<div class="flex items-center gap-3 text-purple-800 font-medium">
						{@html icons.externalLink}
						<span>Sees your screenshots</span>
					</div>
				</div>
			</div>
		</section>

		<!-- Insights to Action Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-orange-100 text-orange-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Planner
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-orange-900 mb-6 tracking-tight">
					From insights to action
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Agents help you break plans down, manage todos, and keep everything moving.
				</p>
			</div>

			<div class="bg-orange-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="bg-white rounded-2xl shadow-sm p-6 md:p-8 max-w-3xl mx-auto">
					<!-- Stats -->
					<div class="grid grid-cols-4 gap-4 mb-8">
						<div class="bg-green-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-green-800 mb-1">Today</div>
							<div class="text-2xl font-bold text-green-900">5</div>
						</div>
						<div class="bg-orange-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-orange-800 mb-1">Scheduled</div>
							<div class="text-2xl font-bold text-orange-900">51</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">All</div>
							<div class="text-2xl font-bold text-gray-900">56</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Completed</div>
							<div class="text-2xl font-bold text-gray-900">70</div>
						</div>
					</div>

					<!-- Task List -->
					<div class="space-y-6">
						<div>
							<div class="text-xs font-bold text-red-500 mb-2 tracking-wide">OVERDUE</div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-red-500 flex items-center justify-center cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Review quarterly budget report</h4>
									<p class="text-xs text-gray-500 mt-1">Review and provide feedback on the Q4 budget analysis prepared by the finance team.</p>
									<div class="text-xs text-red-500 mt-1 font-medium">YESTERDAY · 2:00 PM</div>
								</div>
							</div>
						</div>

						<div>
							<div class="text-xs font-bold text-red-500 mb-2 tracking-wide">TODAY</div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-gray-300 group-hover:border-gray-400 cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">40-min Zone-2 jog / easy spin</h4>
									<p class="text-xs text-gray-500 mt-1">Perform a 40-minute Zone-2 jog or easy spin. Maintain a pace where you can converse in full sentences.</p>
									<div class="flex gap-2 text-xs text-gray-400 mt-1">
										<span>TODAY · 06:00 AM</span>
										<span>•</span>
										<span class="flex items-center gap-1">{@html icons.repeat} REPEATS WEEKLY</span>
									</div>
								</div>
							</div>
						</div>

						<div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-blue-500 cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Team standup meeting</h4>
									<p class="text-xs text-gray-500 mt-1">Daily sync with the team to discuss progress and blockers.</p>
									<div class="text-xs text-gray-400 mt-1">TODAY · 9:00 AM</div>
								</div>
							</div>
						</div>

						<div>
							<div class="text-xs font-bold text-gray-400 mb-2 tracking-wide">NO DUE DATE</div>
							<div class="space-y-3 opacity-60">
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Draft the first cut — 90-min rough draft block</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Feedback loop — sit with Alex and refine the draft</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Badminton practice</span>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row gap-8 md:items-start justify-between">
				<div class="flex gap-6 text-sm font-medium text-gray-600">
					<div class="flex items-center gap-2">
						{@html icons.check}
						<span>Checklists</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.calendar}
						<span>Scheduled events</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.repeat}
						<span>Repeating tasks</span>
					</div>
				</div>
				<p class="text-xl text-gray-600 max-w-lg leading-relaxed">
					Capture an idea, sketch a plan, or think out loud—your agents turn it into an actionable roadmap without disrupting your flow.
				</p>
			</div>
		</section>

		<!-- Who uses it Section -->
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Use cases
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Who uses it?
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Distill works for anyone who needs to keep their best thinking alive- from executives to researchers to creators.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
				<!-- Card 1 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Decision logging</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Record key choices and the reasoning behind them, so you can revisit the "why" at any time.</p>
				</div>
				<!-- Card 2 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Idea tracking</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Capture sparks of inspiration before they fade and connect them to ongoing work.</p>
				</div>
				<!-- Card 3 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Weekly reviews</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Reflect on the past week's shifts, wins, and challenges to plan your next moves.</p>
				</div>
				<!-- Card 4 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Story building</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Develop narratives or arguments over time by adding and refining entries in a thread.</p>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Progress tracking</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Keep a living record of milestones, blockers, and updates across projects.</p>
				</div>
				<!-- Card 6 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Goal setting</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Define clear objectives and keep them visible as your work evolves.</p>
				</div>
				<!-- Card 7 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Action planning</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Turn insights and ideas into a prioritized list of next steps.</p>
				</div>
				<!-- Card 8 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Strategy reviews</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Assess current direction by surfacing shifts, risks, and opportunities.</p>
				</div>

				<!-- Card 9 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Research synthesis</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Convert scattered findings into clear, connected insights.</p>
				</div>
				<!-- Card 10 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Meeting prep</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Walk into discussions with the relevant context and decisions at hand.</p>
				</div>
				<!-- Card 11 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Content outlining</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Shape captured thoughts into structured drafts for writing or presentations.</p>
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
							{@html icons.sparkles} The augmented thinker
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.plus} Getting started with Distill
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.download} Import to Distill
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.target} Make your own agents
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.reflection} Building a journaling habit
						</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center mt-12 pt-8 text-xs text-gray-400">
				<div class="flex items-center gap-2 mb-4 md:mb-0">
					<div class="w-6 h-6 text-gray-300">
						<svg viewBox="0 0 24 24" fill="currentColor" class="w-full h-full">
							<path d="M12 2C13.1 2 14 2.9 14 4C14 5.1 13.1 6 12 6C10.9 6 10 5.1 10 4C10 2.9 10.9 2 12 2ZM12 22C10.9 22 10 21.1 10 20C10 18.9 10.9 18 12 18C13.1 18 14 18.9 14 20C14 21.1 13.1 22 12 22ZM6 12C6 10.9 5.1 10 4 10C2.9 10 2 10.9 2 12C2 13.1 2.9 14 4 14C5.1 14 6 13.1 6 12ZM22 12C22 13.1 21.1 14 20 14C18.9 14 18 13.1 18 12C18 10.9 18.9 10 20 10C21.1 10 22 10.9 22 12ZM17.66 7.34C18.44 6.56 19.7 6.56 20.48 7.34C21.26 8.12 21.26 9.38 20.48 10.16C19.7 10.94 18.44 10.94 17.66 10.16C16.88 9.38 16.88 8.12 17.66 7.34ZM6.34 16.66C5.56 17.44 4.3 17.44 3.52 16.66C2.74 15.88 2.74 14.62 3.52 13.84C4.3 13.06 5.56 13.06 6.34 13.84C7.12 14.62 7.12 15.88 6.34 16.66ZM16.66 17.66C15.88 18.44 15.88 19.7 16.66 20.48C17.44 21.26 18.7 21.26 19.48 20.48C20.26 19.7 20.26 18.44 19.48 17.66C18.7 16.88 18.7 15.62 17.92 14.84L16.66 17.66ZM7.34 6.34C8.12 5.56 8.12 4.3 7.34 3.52C6.56 2.74 5.3 2.74 4.52 3.52C3.74 4.3 3.74 5.56 4.52 6.34C5.3 7.12 6.56 7.12 7.34 6.34Z" />
						</svg>
					</div>
					<div>
						<p>Copyright © 2025 UNMS Technologies Corp.</p>
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

