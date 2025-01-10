<script lang="ts">
	import { base } from '$app/paths';

	let tabs = [
		{ name: 'About', link: '#about' },
		{ name: 'Music', link: 'music' }
	];
</script>

<header>
	<div class="fixed z-[10] h-[75px] w-full bg-black">
		<div class="flex h-full items-center justify-center">
			<div class="z-[11] flex w-full max-w-[1400px] items-center justify-between px-4">
				<h1 class="font-medium">
					<a href="{base}/" target="_self">
						<b class="poppins font-bold">Lua</b> Music
					</a>
				</h1>
				<div class="hidden items-center gap-4 sm:flex">
					{#each tabs as tab}
						<a href="{base}/{tab.link}" class="duration-200 hover:text-green-300">
							<p>{tab.name}</p>
						</a>
					{/each}
					<a
						href="https://bsky.app/profile/luafourteen.bsky.social"
						target="_blank"
						class="luaButton"
					>
						Talk to me &rarr;
					</a>
				</div>
			</div>
		</div>
	</div>
</header>
