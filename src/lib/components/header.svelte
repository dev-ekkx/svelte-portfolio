<script lang="ts">

	import { cn } from '$lib/utils/utils';
	import { page } from '$app/state';
	import { onMount } from 'svelte';

		let activePage = $state("")
	const links = [
	"home", "works", "about-me", "contact"
	]

	onMount(() => {
		activePage = page.url.hash.split("#")[1] ?? " "
	})

	const setActivePage = (page: string) => {
		activePage = page
	}

</script>

<header class="flex items-center justify-between h-[5rem] g-padding">
	<div class="w-max relative">
	<img src="/images/logo.png" alt="logo" class="w-20">
	<span class="text-2xl text-white font-link text-[0.9rem] absolute -right-11 top-2/5">Dela Ricch</span>
	</div>
	<nav>
		<ul class="flex items-center gap-4">
			{#each links as link (link)}
			<li class="relative">
					<span class={cn("absolute w-0 left-0 bottom-0.5 h-0.5 bg-secondary transition-all duration-200 ease-linear", {
				"w-full": link === "home" ? activePage === " " : activePage === `${link}`,

					})}></span>
				<a
					onclick={() => setActivePage(link === 'home' ? ' ' : `${link}`)}
					href={link === "home" ? "/" : `#${link}`}
					 class={cn("font-link text-white flex capitalize hover:text-secondary transition-all", {
				"text-secondary": link === "home" ? activePage === " " : activePage === `${link}`,
			})}>

				<span class="font-semibold">#</span>
					<span>
						{link.split("-").join(" ")}
					</span>
				</a>
			</li>
			{/each}
		</ul>
	</nav>
</header>