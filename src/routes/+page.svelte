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
				<h2 in:fade="{{ duration: 500, delay: 200 }}" class="text-4xl sm:text-6xl font-bold mb-4 z-10 pointer-events-none">
					Another World is Possible
				</h2>
				<div class=" rounded-[25px] overflow-hidden m-[10px] pointer-events-auto z-50">
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
		  class="w-full h-auto rounded-lg mb-4 z-50"
		/>
	  </div>
	</section>
  
	<section id="TheProject" class=" py-48 text-blue-950 z-50 bg-teal-500 h-full">
	  <div class="container mx-auto px-4">
		<h3 class="text-3xl font-black mb-12 text-right">The Project</h3>
		<div class="grid grid-cols-1 gap-8">
		  <div>
			<img
			src={bhScene1}
			alt="Behind the scenes 1"
			class="w-full h-auto rounded-lg mb-4"
			/>
			<p class="font-bold py-2 pb-10 p-5 rounded-md text-white md:text-xl text-sm ">Embark on a cinematic journey unlike any other. Our documentary series intricately weaves together the most pressing social, ecological, and economic crises of our time, unveiling the SYSTEM that drives these challenges and hinders real change. But this isn’t just a critique; it’s a visionary roadmap toward a NEW system—one that aspires to save our world.
				Prepare for a dynamic odyssey bursting with drama, excitement, and mind-blowing ideas. Filmed across 16 U.S. states and 3 continents, our series features vibrant characters from all walks of life—from passionate youth in revolt to esteemed professors, scientists, activists, and indigenous leaders. You'll hear from legends like Noam Chomsky and countless other prominent figures, all voicing the urgent need for radical change and showcasing real-world solutions that demonstrate a better future is within reach.
				Through compelling storytelling, we explore our disconnection from nature, the historical roots of our current crises, and the possibilities and threats posed by technology. We shine a light on the various global movements advocating for change and rethinking everything—from currency and governance to food systems and societal organization. This series is a thrilling blend of dystopian narrative, action, and nature documentary, all while remaining deeply character-driven and hopeful.
				Join us as we take viewers on a wild ride from bustling financial centers to ancient indigenous villages and into the innovative pockets of the future around the globe. This series is led by experts and driven by community voices, presenting a real-life adventure filled with optimistic solutions to humanity’s biggest challenges.
				This is not just a film; it’s a planetary story that connects us all. With successive interconnected narratives, we aim to inspire a grassroots movement and actionable, nonviolent plans for a regenerative cooperative transition. Together, we can spark direct change and foster a vision of unity over division.
				This is a film to change the world. Nothing less. Join us in making it happen!</p>
		</div>
	  </div>
		<div class="flex md:flex-row flex-col">
			<img
				src={bhScene2}
				alt="Behind the scenes 2"
				class="md:w-1/2 h-auto rounded-lg mb-4 object-cover m-4"
			/>
			<div class="my-6">
				<p id="WhatImlookingforrightnow" class="font-black text-2xl"> What Im looking for right now.</p>
				<p class="text-white font-bold pt-16 p-10 rounded-md bg-black bg-opacity-10 my-9 h-full md:text-xl text-sm">I’ve poured my heart and soul into this film, tackling complex systemic issues with nothing but determination and resourcefulness. With virtually no budget, I’ve captured over 20 terabytes of breathtaking footage and completed 80% of the series, all while facing countless adventures along the way.
					Now, I’m reaching out for your support to take this project to the next level. I need a small amount of funding to shoot the final segments on a global scale, filming some of the world’s most impactful projects abroad. Your assistance in securing a few high-profile interviews would be invaluable—I’ve achieved incredible things without connections, so imagine what we could accomplish together!
					Here’s what I need:
					<br/> <br/>
					Funding: Just enough to cover travel costs as I continue to work with my own gear and on a shoestring budget. If you believe in the vision Im ready to go further too.
					<br/> <br/>
					Production Support: I’m seeking a producer and a dedicated team to assist with post-production. Specifically, I need at least one assistant/co-editor to help structure and organize the footage, ensuring it’s ready for distribution on major platforms like Netflix or HBO.
					I have a clear roadmap to craft this into the most epic story ever told, but I can’t do it alone. If you believe in the power of storytelling and want to be part of this journey, your support means the world to me.
					Let’s bring this vision to life together!
					</p>
			</div>
		</div>
	</section>
  
</div>