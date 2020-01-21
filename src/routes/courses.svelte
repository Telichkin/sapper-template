<script context="module">
	export async function preload({ params, query }) {
		const res = await this.fetch(`courses.json`);
		const courses = await res.json();
		return { courses };
	}
</script>

<script>
	export let courses; 
</script>


<svelte:head>
	<title>Курсы</title>
</svelte:head>

<div class="container px-6 pt-5 sm:px-10 sm:pt-8">
	<h1 class="text-2xl text-gray-800 font-bold mb-4">Идет набор</h1>
	<ul class="md:flex md:-mx-4 md:flex-wrap md:align-bottom">
		{#each courses as course}
		<li class="md:px-4 py-3 md:w-1/2">
			<div class="flex flex-col h-full p-4 bg-white rounded shadow-md">
				<h2 class="text-xl font-medium mb-2">
					{course.name}
				</h2>
				<p class="mb-4 font-normal">
					{course.descr}
				</p>
				<ul class="text-sm font-light mb-3">
					{#each course.about as info}
					<li class="mb-1">
						{info}
					</li>
					{/each}
				</ul>
				<div class="flex flex-1 justify-end items-end">
					<a href="." class="block py-2 px-5 bg-blue-500 rounded shadow-md text-white text-sm font-medium">
						Купить
					</a>
					<a href="." class="block ml-4 py-2 px-5 bg-gray-300 rounded text-gray-700 text-sm font-normal">
						Подробнее
					</a>
				</div>
			</div>
		</li>
		{/each}
	</ul>

	<h1 class="text-2xl text-gray-800 font-bold mt-12 mb-4">Набор окончен</h1>
	<ul class="md:flex md:-mx-4 md:flex-wrap md:align-bottom">
		<li class="md:px-4 py-3 md:w-1/2">
			<div class="flex flex-col h-full p-4 bg-gray-200 rounded shadow-md">
				<h2 class="text-xl font-medium mb-2">
					{courses[1].name}
				</h2>
				<p class="mb-4 font-normal">
					{courses[1].descr}
				</p>
				<ul class="text-sm font-light mb-3">
					{#each courses[1].about as info}
					<li class="mb-1">
						{info}
					</li>
					{/each}
				</ul>
				<div class="flex flex-1 justify-end items-end">
					<a href="." class="block py-2 px-5 bg-blue-200 rounded text-white text-sm font-medium cursor-not-allowed">
						Купить
					</a>
					<a href="." class="block ml-4 py-2 px-5 bg-gray-300 rounded text-gray-700 text-sm font-normal">
						Подробнее
					</a>
				</div>
			</div>
		</li>
	</ul>
</div>