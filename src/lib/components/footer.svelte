<script lang="ts">
	import LogoComponent from '$lib/components/logo.svelte';
	import { socialMediaLinks } from '$lib/constants';


</script>

<footer class="py-8 border-t-4 g-padding border-white flex flex-col gap-6">
	<section class="flex items-center justify-between">
		<div class="flex flex-col">
			<div class="flex gap-6 items-center">
				<LogoComponent />
				<span>devekkx@gmail.com</span>
			</div>
			<span class="text-white">Front-end engineer and solutions architect</span>
		</div>

	<div class="flex flex-col gap-2">
	<span class="capitalize font-bold text-xl text-white">media</span>
		<div class="flex items-center gap-2 flex-wrap">
			{#each socialMediaLinks as link(link.name)}
				<a href={link.url} target="_blank" rel="noopener noreferrer" aria-label={link.name} class="bg-white p-0.5 rounded-md group">
				<img src={link.icon} alt={`${link.name}-logo`} class="w-6 h-auto group-hover:scale-110 transition-all duration-200 ease-linear" />
				</a>
				{/each}
		</div>
	</div>
	</section>
</footer>