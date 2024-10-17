<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import { Menu, X} from 'lucide-svelte';
	import '../app.css';
	let isMenuOpen = false;
	
	let cursorX = 0;
	let cursorY = 0;
	onMount(() => {
	  const handleMouseMove = (e: MouseEvent) => {
		cursorX = e.clientX;
		cursorY = e.clientY;
	  };
  
	  window.addEventListener('mousemove', handleMouseMove);
  
	  return () => {
		window.removeEventListener('mousemove', handleMouseMove);
	  };
	});
</script>

  
<svelte:head>
	<title>Another World is Possible</title>
</svelte:head>
	<div class=" min-h-screen max-w-screen overflow-hidden">

		<nav class="fixed top-0 left-0 w-full z-40 text-white bg-black mix-blend-difference">
			<div class=" w-full h-max mx-auto px-4 py-6 flex justify-between items-center">
				<h1 in:fade="{{ duration: 500 }}" class="text-2xl font-bold">
					Another World is Possible
				</h1>
				<button on:click={() => (isMenuOpen = !isMenuOpen)}>
					{#if isMenuOpen}
					<X size={24} class="z-50" />
					{:else}
					<Menu size={24} class="z-50 " />
					{/if}
				</button>
			</div>	
		</nav>
		
		{#if isMenuOpen}
		<div
		in:fly="{{ x: '100%', duration: 300 }}"
		out:fly="{{ x: '100%', duration: 300 }}"
		class="fixed top-0 right-0 w-full sm:w-64 h-full text-white bg-red bg-black bg-opacity-90 z-30 flex items-center justify-center"
		>
			<ul class="text-center space-y-8">
				<li><a href="#synopsis" class="text-2xl hover:text-gray-300 transition-colors">Synopsis</a></li>
				<li><a href="#behind-the-scenes" class="text-2xl hover:text-gray-300 transition-colors">Behind the Scenes</a></li>
				<li><a href="#support" class="text-2xl hover:text-gray-300 transition-colors">Support</a></li>
			</ul>
		</div>
	{/if}
	<div
	class="fixed w-8 h-8 rounded-full border-2 border-white pointer-events-none z-40 mix-blend-difference"
	style="transform: translate(-50%, -50%); left: {cursorX}px; top: {cursorY}px;"
	/>
	
	<main>
		<slot />
	</main>
	
	<footer class="bg-black min-h-[60vh] py-12">
		<div class="container mx-auto px-4 text-center">
			<p class="mb-4">&copy; 2024 Another World is Possible. All rights reserved.</p>
			<div class="flex justify-center space-x-4">
				<a href="/" class="hover:text-gray-300 transition-colors">Facebook</a>
				<a href="/" class="hover:text-gray-300 transition-colors">Twitter</a>
				<a href="/" class="hover:text-gray-300 transition-colors">Instagram</a>
			</div>
		</div>
	</footer>
	
</div>
	<style>
		:global(html) {
			scroll-behavior: smooth;
	}
</style>