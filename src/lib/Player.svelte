<script lang="ts">
	import { onMount } from 'svelte';
	import YoutubePlayer from 'youtube-player';

	export let videoId: string;
	$: player && player.loadVideoById(videoId);

	let player;
	let options = {
		playerVars: {
			autoplay: 1
		}
	};

	onMount(() => {
		player = YoutubePlayer(player, options);
		player.loadVideoById(videoId);
		setTimeout(()=>{
            player.playVideo();
        }, 2000)
	});
</script>


<div id="youtube-player" class="w-full h-full" bind:this={player} />

