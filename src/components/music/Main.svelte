<script lang="ts">
	import { cubicOut } from 'svelte/easing';
	import { tracksStore } from '../../stores/tracks';
	import { scale, fade } from 'svelte/transition';

	let tracks = $tracksStore?.tracks;

	let showModal = $state(false);
	let selectedImage = $state('');

	function openModal(imageSrc: string) {
		selectedImage = imageSrc;
		showModal = true;
	}

	function closeModal(event: Event) {
		if (event.target === event.currentTarget) {
			showModal = false;
		}
	}
</script>

<main class="flex flex-col items-center justify-center px-24">
	{#if tracks}
		{#each tracks as track, i}
			<div
				class="flex h-screen w-[80%] flex-col items-center justify-center gap-x-24 gap-y-12 md:flex-row"
			>
				<div>
					<!-- svelte-ignore a11y_click_events_have_key_events -->
					<!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
					<img
						src="../images/{track.filename}"
						alt="Track Art"
						class="whiteGlow max-h-[80vh] transform cursor-pointer transition-transform duration-200 ease-in-out hover:scale-110"
						onclick={() => openModal('../images/' + track.filename)}
					/>
				</div>
				<div class="flex flex-col justify-center gap-8">
					<h2 class="text-4xl font-semibold sm:text-5xl md:text-6xl">
						{track.name}
					</h2>
					<p>{track.description}</p>
					<div class="max-w-[400px]">
						<a href={track.link} target="_blank" class="luaButton"> Listen on Spotify &rarr;</a>
					</div>
				</div>
			</div>
		{/each}
	{/if}

	{#if showModal}
		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div
			class="fixed inset-0 z-[8] flex items-center justify-center bg-black bg-opacity-75"
			transition:fade={{ duration: 300 }}
			onclick={closeModal}
		>
			<!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
			<img
				src={selectedImage}
				alt="Enlarged"
				class="z-[9] max-w-[90vw] object-contain md:max-w-[40vw]"
				onclick={closeModal}
			/>
		</div>
	{/if}
</main>
