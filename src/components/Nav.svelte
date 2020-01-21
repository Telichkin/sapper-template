<script>
	export let segment;
</script>

<nav>
	<ul>
		<li>
			<a class:selected='{segment === undefined}' href='.'>МОШка</a>
		</li>
		<li>
			<a class:selected='{segment === "courses"}' href='courses'>Курсы</a>
		</li>

		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<li>
			<a rel=prefetch class:selected='{segment === "blog"}' href='blog'>Статьи</a>
		</li>
	</ul>
</nav>

<style lang="postcss">
	nav {
		@apply font-light text-sm px-1 border-b border-gray-300;
	}

	ul {
		@apply flex;
	}

	a {
		@apply block p-4 outline-none;
	}

	.selected {
		@apply border-blue-400 border-b-2;
	}
</style>
