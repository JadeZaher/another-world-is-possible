<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly, slide  } from 'svelte/transition';
	import { tap } from 'svelte-gestures';
	import { Menu, X } from 'lucide-svelte';
	import earth from '$lib/images/Rotating_earth_animated_transparent.gif'
	import '../app.css';
	let isMenuOpen:boolean = false;
	let isLoaded:boolean = false;
	
	let cursorX:number = 0;
	let cursorY:number = 0;
	let width:number = 0;

	let lastScrollY = 0;
	let visible = false;

	const handleScroll = () => {
		const currentScrollY = window.scrollY;
		visible = (currentScrollY <= lastScrollY || currentScrollY < 100); // Show on scroll up or top

		lastScrollY = currentScrollY;
	};

	onMount(() => {
		const handleMouseMove = (e: MouseEvent) => {
			cursorX = e.clientX;
			cursorY = e.clientY;
		};
		
		window.addEventListener('scroll', handleScroll);
		window.addEventListener('mousemove', handleMouseMove);
		
		return () => {
		window.removeEventListener('scroll', handleScroll);
		window.removeEventListener('mousemove', handleMouseMove);
	  };
	});
	const handleOnLoad = () : void => {
		isLoaded = true;
	};
</script>

  
<svelte:head>
	<title>Another World is Possible</title>
</svelte:head>
<svelte:window on:load="{()=>handleOnLoad()}" bind:outerWidth={width}/>
	<img src={earth} class=" z-30 zbas pointer-events-none fixed left-[10px] duration-[3s] ease-out mix-blend-normal"
	style="width:{"10%"}; top:{"10%" };left:{(lastScrollY > 400 && lastScrollY < 5000 ? 90: lastScrollY / 1000 + 5 )}%;"
	alt="" srcset=""/>
	
	<div class=" min-h-screen max-w-screen overflow-hidden">
		<nav class={` pointer-events-auto z-[101] fixed top-0 left-0 w-full text-white bg-black duration-[.2s] ease-linear mix-blend-difference`}>
			<div class=" w-full h-max mx-auto px-4 py-6 flex justify-between items-center cursor-pointer">
				<button class=" z-[100] w-full"  on:click={() => (isMenuOpen = !isMenuOpen)} on:tap={() => (isMenuOpen = !isMenuOpen)} >
					{#if isMenuOpen}
					<X size={24} class="z-[102]" />
					{:else}
					<Menu size={24} class="z-[101] " />
					{/if}
				</button>
			</div>	
		</nav>
		
		{#if isMenuOpen}
		<div
		in:fly="{{ x: '100%', duration: 300 }}"
		out:fly="{{ x: '100%', duration: 300 }}"
		class="fixed top-0 right-0 w-full max-w-4xl px-10 h-full text-white bg-red bg-black bg-opacity-60 z-[101] flex items-center justify-center rounded-[2rem]"
		>
			<ul class="text-center space-y-8 flex justify-start flex-col">
				<a href="#start" class="text-2xl  transition-colors">
					<button class=" border-b-[1px] h-full w-full rounded-[5px] hover:text-green-300 p-2 bg-blend-color-burn bg-white text-black font-black shadow-slate-200 border-green-400 rounded-lb-md drop-shadow-sm" on:click={()=>(isMenuOpen = !isMenuOpen)} on:tap={()=>(isMenuOpen = !isMenuOpen)}>
						Start
					</button>
					</a>
				<a href="#synopsis" class="text-2xl  transition-colors">
				<button class=" border-b-[1px] h-full w-full rounded-[5px] hover:text-green-300 p-2 bg-blend-color-burn bg-white text-black font-black shadow-slate-200 border-green-400 rounded-lb-md drop-shadow-sm" on:click={()=>(isMenuOpen = !isMenuOpen)} on:tap={()=>(isMenuOpen = !isMenuOpen)}>
					Synopsis
				</button>
				</a>
				<a href="#TheProject" class="text-2xl  transition-colors">
				<button class=" border-b-[1px] h-full w-full rounded-[5px] hover:text-green-300 p-2 bg-blend-color-burn bg-white text-black font-black shadow-slate-200 border-green-400 rounded-lb-md drop-shadow-sm" on:click={()=>(isMenuOpen = !isMenuOpen)} on:tap={()=>(isMenuOpen = !isMenuOpen)}>
					The Project
				</button>
				</a>
				<a href="#WhatImlookingforrightnow" class="text-2xl  transition-colors">
				<button class=" border-b-[1px] h-full w-full rounded-[5px] hover:text-green-300 p-2 bg-blend-color-burn bg-white text-black font-black shadow-slate-200 border-green-400 rounded-lb-md drop-shadow-sm" on:click={()=>(isMenuOpen = !isMenuOpen)} on:tap={()=>(isMenuOpen = !isMenuOpen)}>
					What We Need
				</button>
				</a>
			</ul>
		</div>
	{/if}
	<div
	class="fixed w-8 h-8 rounded-full border-2 border-white pointer-events-none  z-[100] mix-blend-difference"
	style="transform: translate(-50%, -50%); left: {cursorX}px; top: {cursorY}px;"
	/>
	
	<main>
		<slot />
	</main>
	
	<footer class="bg-black text-white h-[10vh]">
		<div class="container mx-auto px-4 text-center">
			<p class="mb-4">&copy; 2024 Another World is Possible. All rights reserved.</p>
		</div>
	</footer>
	
</div>
	<style>
		:global(html) {
			scroll-behavior: smooth;
	}
</style>