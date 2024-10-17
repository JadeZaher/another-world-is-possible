<script lang="ts">
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';
	import { Play, Pause } from 'lucide-svelte';
  
	let isVideoPlaying = true;
	let videoElement: HTMLVideoElement;
  
	function toggleVideo() {
	  if (videoElement) {
		if (isVideoPlaying) {
		  videoElement.pause();
		} else {
		  videoElement.play();
		}
		isVideoPlaying = !isVideoPlaying;
	  }
	}
</script>

<div class="relative min-h-screen w-screen bg-black text-white overflow-hidden">

	<section class="relative h-screen">
	  <video
		bind:this={videoElement}
		autoplay
		loop
		muted
		playsinline
		class="absolute top-0 left-0 w-full h-full object-cover"
	  >
		<!-- <source src="/placeholder.mp4" type="video/mp4" /> -->
	  </video>
	  <div class="absolute inset-0 bg-black bg-opacity-50 flex items-center justify-center">
		<div class="text-center">
		  <h2 in:fade="{{ duration: 500, delay: 200 }}" class="text-4xl sm:text-6xl font-bold mb-4">
			Another World is Possible
		  </h2>
		  <p in:fade="{{ duration: 500, delay: 400 }}" class="text-xl sm:text-2xl mb-8">
			A journey beyond imagination
		  </p>
		  <button
			in:fade="{{ duration: 500, delay: 600 }}"
			class="bg-white text-black px-8 py-3 rounded-full text-lg font-semibold hover:bg-opacity-90 transition-colors"
		  >
			Watch Trailer
		  </button>
		</div>
	  </div>
	  <button
		on:click={toggleVideo}
		class="absolute bottom-8 right-8 bg-white bg-opacity-20 p-2 rounded-full hover:bg-opacity-30 transition-colors"
	  >
		{#if isVideoPlaying}
		  <Pause size={24} />
		{:else}
		  <Play size={24} />
		{/if}
	  </button>
	</section>
  
	<section id="synopsis" class="py-24 bg-gray-900">
	  <div class="container mx-auto px-4">
		<h3 class="text-3xl font-bold mb-8">Synopsis</h3>
		<p class="text-lg leading-relaxed">
		  "Another World is Possible" takes viewers on a breathtaking journey through alternate realities, challenging our perception of what's possible. As the boundaries between worlds blur, our protagonists must navigate the consequences of their choices across multiple dimensions, ultimately discovering that the key to saving their own world lies in the connections they forge across the multiverse.
		</p>
	  </div>
	</section>
  
	<section id="behind-the-scenes" class="py-24 bg-gray-900">
	  <div class="container mx-auto px-4">
		<h3 class="text-3xl font-bold mb-12">Behind the Scenes</h3>
		<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
		  <div>
			<img
			  alt="Behind the scenes 1"
			  class="w-full h-auto rounded-lg mb-4"
			/>
			<p class="text-lg">Capturing the essence of multiple worlds on set.</p>
		  </div>
		  <div>
			<img
			  alt="Behind the scenes 2"
			  class="w-full h-auto rounded-lg mb-4"
			/>
			<p class="text-lg">The visual effects team bringing alternate realities to life.</p>
		  </div>
		</div>
	  </div>
	</section>

	<section id="support" class="py-24 bg-black">
		<div class="container mx-auto px-4">
		  <h3 class="text-3xl font-bold mb-12">Support</h3>
		  <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-8">
			{#each [1, 2, 3, 4] as i}
			  <div class="text-center">
				<img
				  alt="Support Option {i}"
				  class="w-full h-auto rounded-lg mb-4"
				/>
				<h4 class="text-xl font-semibold">Support</h4>
				<p class="text-gray-400">Support</p>
			  </div>
			{/each}
		  </div>
		</div>
	  </section>

  
</div>