<script>
import { stores } from '@sapper/app';

const { preloading } = stores();
</script>

<main class="relative bg-gray-100 w-full min-h-screen">
	{#if $preloading}
		<div class="fixed top-0 w-full h-1 z-50">
			<div class="progress relative w-40 h-full bg-blue-400"></div>
		</div>
	{/if}
	<slot></slot>
</main>

<style lang="postcss">
	.progress {
		animation: progress 2.1s cubic-bezier(0.18, 0.49, 0.71, 0.4) infinite;
	}

	@keyframes progress {
		0% {
			left: -35%;
			right: 100%;
		}
		60% {
			left: 100%;
			right: -90%;
		}
		100% {
			left: 100%;
			right: -90%;
		}
	}
</style>