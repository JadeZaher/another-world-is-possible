<script lang="ts">
	import { fade } from 'svelte/transition';
	import { Youtube } from 'svelte-youtube-lite';
	import synopsis from "$lib/images/awp-img1.png";
	import bhScene1 from "$lib/images/awp-img2.png";
	import bhScene2 from "$lib/images/awp-img3.png";
    const videoId = 'T7Gr3dljEVE'; // Replace with your actual video ID  
</script>

<div class="relative min-h-screen w-screen flex flex-col justify-center bg-white text-black overflow-hidden">

	<section class="relative h-screen">
		<div  id="start" class="absolute inset-0 flex items-center justify-center pointer-events-none z-20 drop-shadow-2xl">
			<div class="text-center">
				<h2 in:fade="{{ duration: 500, delay: 200 }}" class="text-4xl sm:text-6xl font-bold mb-4 pointer-events-none">
					Another World is Possible
				</h2>
				<div class=" rounded-[25px] overflow-hidden m-[10px] pointer-events-auto">
					<Youtube id={videoId} showTitle="{false}"  />
				</div>
		  <p in:fade="{{ duration: 500, delay: 400 }}" class="text-xl sm:text-2xl mb-8">
			By Zachary Marlow
		  </p>
		</div>
	
	</div>

	</section>
  
	<section id="synopsis" class="py-24 text-blue-300 w-full bg-teal-700 min-h-[80vh]">
	  <div class="container mx-auto px-4">
		<h3 class="text-3xl font-bold mb-8">Synopsis</h3>
		<p class="text-lg leading-relaxed py-10">
			"Another World is Possible". <br/>
			All that means is we explore alternative ways we can be structuring our world. 
			We have evolved the ability to shape our own reality more than any species on this planet. 
			We are responsible and capable of so much. 
			When we come together in the right ways for the right reasons we can do all goods and undo all evils.
			But when we fail to do that we can end up facing disasterous conflicts.
		</p>
		<img
		src={synopsis}
		  alt="Behind the scenes 1"
		  class="w-full h-auto rounded-lg mb-4"
		/>
	  </div>
	</section>
  
	<section id="behind-the-scenes" class=" py-48 text-blue-950 z-50 bg-teal-500 h-full">
	  <div class="container mx-auto px-4">
		<h3 class="text-3xl font-bold mb-12">We will look everywhere</h3>
		<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
		  <div>
			<img
			src={bhScene1}
			alt="Behind the scenes 1"
			class="w-full h-auto rounded-lg mb-4"
			/>
			<p class="text-lg">For struggle and what we can do now to change it.</p>
		</div>
		<div>
			<img
			src={bhScene2}
			  alt="Behind the scenes 2"
			  class="w-full h-auto rounded-lg mb-4"
			/>
			<p class="text-lg">Listening people with a story, a vision, and a path forward for the world together.</p>
		  </div>
		</div>
	  </div>
	</section>
  
</div>