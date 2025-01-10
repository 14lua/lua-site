<script lang="ts">
	import { tracksStore } from '../stores/tracks';
	import { base } from '$app/paths';

	let tracks = $tracksStore?.tracks;
	let firstTrackFilename: string = tracks ? tracks[0].filename : '';
</script>

<main class="flex flex-1 flex-col items-center justify-center p-4">
	<section
		id="home"
		class="mt-24 flex h-screen w-[80%] max-w-[1400px] flex-col flex-nowrap items-center gap-12 sm:py-14 lg:m-0 lg:flex-row lg:justify-between"
	>
		<div class="flex flex-col gap-6 text-center md:gap-8 lg:justify-center lg:gap-10 lg:text-left">
			<h2 class="pr-12 text-4xl font-semibold sm:text-5xl md:text-6xl">
				Welcome to the<br /><span class="poppins text-green-700"> dark side of the moon </span>
			</h2>
			<p class="text-base sm:text-lg md:text-xl">
				Thank you for visiting <i class="fa-solid fa-heart"></i>
			</p>
		</div>
		<div
			class="realtive flex transform place-items-center shadow-2xl transition-transform ease-in-out hover:scale-105"
		>
			<a href="{base}/music" target="_self">
				<img
					src="images/{firstTrackFilename}"
					alt="Latest Cover"
					class="whiteGlow z-[2] max-h-[50vh] object-cover blur-sm duration-300 ease-in-out hover:blur-none"
				/>
			</a>
		</div>
	</section>

	<section id="about" class="flex h-screen max-w-[1400px] flex-col items-center justify-center">
		<div class="flex flex-col items-center justify-center gap-16">
			<div class="flex flex-col gap-2 text-center">
				<h6 class="text-lg sm:text-xl md:text-2xl">Who even am I?</h6>
				<h3 class="text-3xl font-semibold sm:text-4xl md:text-6xl">
					I go by the name <span class="poppins text-green-700">Lua</span>
				</h3>
			</div>
			<div>
				<p class="text-justify text-base font-medium md:text-lg lg:text-2xl">
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur, doloribus. Pariatur
					maiores, quos illo aut id recusandae eveniet repudiandae laboriosam nemo libero ab
					dignissimos inventore facilis deleniti minima quia ex cumque. Omnis sit earum, adipisci
					ratione debitis eos! Id veniam repudiandae, soluta nemo itaque, quam voluptatum molestiae
					architecto esse et ut voluptate eum cupiditate mollitia unde! Doloribus quo, distinctio
					illo laboriosam nemo cumque aspernatur illum deserunt facilis minima sapiente sint
					voluptatum ipsam. Doloribus cumque saepe omnis delectus ex, repellendus, doloremque neque
					sequi fugiat veritatis aperiam ab hic natus explicabo dolores aliquid quis dolore quam
					inventore fuga laudantium. Tempore sit facilis aliquam ullam officia, dolorum mollitia
					provident ut molestias modi accusamus id unde nostrum necessitatibus consequuntur, illo
					officiis omnis assumenda hic ab? Amet corporis ea vitae esse similique! Autem modi velit
					maxime sapiente fugiat inventore, eum ratione rem quisquam, minus, nulla aspernatur
					eveniet. Delectus assumenda nisi architecto. Aliquam neque cupiditate consequatur ipsam
					asperiores non, id est a doloribus beatae dignissimos accusamus omnis voluptatibus magnam!
					Dicta incidunt minima reiciendis. Alias assumenda pariatur debitis autem. Saepe laborum
					dicta assumenda cupiditate harum tenetur, reprehenderit impedit modi perferendis
					voluptates iusto sunt distinctio est ad dolore voluptatem libero quod dolorem repellendus!
					Consequuntur dolore nulla minima laudantium?
				</p>
			</div>
			<div>
				<a href="{base}/music" target="_self" class="luaButton"> My music so far &rarr; </a>
			</div>
		</div>
	</section>
</main>
