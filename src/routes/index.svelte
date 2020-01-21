<script>
	let links = [
		'Dashboard',
		'Jobs',
		'Applicants',
		'Company',
	];

	let timeline = [
		['blue', 'Applied to Backend Developer', 'Aug 26'],
		['blue', 'Advanced to phone screening', 'Aug 26'],
		['green', 'Completed phone screening', 'Sep 2'],
		['blue', 'Advanced to interview', 'Sep 3'],
	];
</script>

<svelte:head>
	<title>Sapper project template</title>
</svelte:head>

<header class="bg-gray-800">
	<div class="flex justify-between items-center w-full m-auto sm:max-w-xl md:max-w-2xl lg:max-w-4xl xl:max-w-6xl text-sm">
		<ul class="flex">
			{#each links as link}
			<li class="py-4 px-6 text-gray-200">
				<a href="/courses">{link}</a>
			</li>
			{/each}
		</ul>
		<ul class="flex items-center">
			<li class="flex items-center rounded bg-gray-900 font-thin w-48">
				<svg class="inline-block fill-current text-gray-500 w-4 h-4 ml-3" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
					<path d="M12.9 14.32a8 8 0 1 1 1.41-1.41l5.35 5.33-1.42 1.42-5.33-5.34zM8 14A6 6 0 1 0 8 2a6 6 0 0 0 0 12z"/>
				</svg>
				<input class="p-2 bg-gray-900 text-gray-400 text-xs outline-none" placeholder="Search" />
			</li>
			<li class="mx-8">
				<svg class="flex-1 inline-block fill-current text-gray-500 w-5 h-5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
					<path d="M4 8a6 6 0 0 1 4.03-5.67 2 2 0 1 1 3.95 0A6 6 0 0 1 16 8v6l3 2v1H1v-1l3-2V8zm8 10a2 2 0 1 1-4 0h4z"/>
				</svg>
			</li>
			<li class="w-8 h-8">
				<img class="rounded-full h-full" alt="User Avatar" src="/user-pic.jpg" />
			</li>
		</ul>
	</div>
</header>

<div class="bg-white shadow">
	<div class="flex justify-between items-center w-full m-auto py-5 sm:max-w-xl md:max-w-2xl lg:max-w-4xl xl:max-w-6xl">
		<div>
			<div class="flex items-center mb-3 font-thin text-gray-600 text-sm">
				<svg class="inline-block fill-current text-gray-500 w-4 h-4 mr-1 -ml-1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
					<path d="M7.05 9.293L6.343 10 12 15.657l1.414-1.414L9.172 10l4.242-4.243L12 4.343z"/>
				</svg>
				<span>
					Педагог-психолог
				</span>
			</div>
			<div class="flex items-center">
				<img class="h-12 w-12 rounded-full mr-3" alt="Photo" src="/user-pic.jpg">
				<h2 class="font-extrabold text-3xl text-gray-900">
					Наталья Маженова
				</h2>
			</div>
		</div>
		<div class="flex">
			<button class="mr-3 px-3 py-1 border-2 border-gray-200 text-gray-600 text-sm font-medium rounded">
				Disqualify
			</button>
			<button class="px-3 py-1 border-2 border-blue-700 bg-blue-700 text-gray-200 text-sm font-medium rounded">
				Advance to offer
			</button>
		</div>
	</div>
</div>

<div class="flex w-full m-auto mt-6 pb-6 sm:max-w-xl md:max-w-2xl lg:max-w-4xl xl:max-w-6xl">
	<div class="w-2/3 pr-6">
		<h2 class="card-header">
			Overview
		</h2>
		<div class="card">
			<div class="flex flex-wrap">
				<div class="overview-item">
					<p class="font-medium text-sm text-gray-500 mb-1">
						Application for
					</p>
					<p class="text-gray-900">
						Backend Developer
					</p>
				</div>
				<div class="overview-item">
					<p class="font-medium text-sm text-gray-500 mb-1">
						Salary Expectation
					</p>
					<p>
						$120,000
					</p>
				</div>
				<div class="overview-item">
					<p class="font-medium text-sm text-gray-500 mb-1">
						Email
					</p>
					<p class="text-gray-900">
						roman@telichk.in
					</p>
				</div>
				<div class="overview-item">
					<p class="font-medium text-sm text-gray-500 mb-1">
						Phone
					</p>
					<p class="text-gray-900">
						+7 (921) 410-72-82
					</p>
				</div>
			</div>
		</div>

		<h2 class="card-header mt-8">
			Notes
		</h2>
		<div class="card">
			<ul>
				{#each Array(2) as _}
				<li class="flex items-start p-6 -mx-6 border-b border-gray-300">
					<div class="w-10 h-10 bg-blue-300 rounded-full"></div>
					<div class="flex-1 ml-4">
						<h2 class="font-semibold mb-2">
							Наталья Маженова
						</h2>
						<p class="text-gray-600 mb-3">
							В пятом и шестом классе наложение одного неосвоенного материала на другой снижает интерес, мотивацию и самооценку. У ребенка появляется неуверенность в себе и своих способностях.
						</p>
						<p class="text-sm text-gray-600">
							<span>4 дня назад</span>
							<span class="mx-1">·</span>
							<span>Ответить</span>
						</p>
					</div>
				</li>
				{/each}
			</ul>
		</div>
	</div>
	<aside class="flex-1">
		<h2 class="card-header">
			Timeline
		</h2>
		<div class="card">
			<ul>
				{#each timeline as [c, t, d]}
				<li class="flex items-center">
					<div class="w-6 h-6 mr-4 bg-{c}-300 rounded-full"></div>
					<div class="flex justify-between flex-1 py-6 -mr-6 border-b border-gray-400 text-sm">
						<span class="w-8/12">{t}</span>
						<span class="text-gray-500 font-medium pl-1 pr-6">{d}</span>
					</div>
				</li>
				{/each}
			</ul>
			<button class="px-3 py-1 mt-6 w-full border-2 border-blue-700 bg-blue-700 text-gray-200 text-sm font-medium rounded">
				Advance to offer
			</button>
		</div>
	</aside>
</div>

<style lang="postcss">
	.card-header {
		@apply text-gray-900 text-base font-semibold mb-3;
	}

	.card {
		@apply bg-white rounded p-6 pt-0 shadow;
	}

	.overview-item {
		@apply w-1/2 mt-6;
	}

	.overview-item:nth-child(odd) {
		@apply pr-1;
	}
</style>
