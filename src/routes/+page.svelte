<script>
	import BooploopsText from '$lib/BooploopsText.svelte';
	import Jukebox from '$lib/Jukebox.svelte';
	import Player from '$lib/Player.svelte';
</script>

<svelte:head>
	<title>booploops</title>
	<meta name="description" content="booploops website" />
</svelte:head>

<div class="placeholder-main">
	<div class="text-container">
		<div class="text-main">
			<BooploopsText />
		</div>
		<div class="text-radient">
			<BooploopsText />
		</div>
	</div>
	<!-- shit for later -->
	<!-- <Jukebox />
	<div id="player_container">
		<Player videoId="DAfh2F4HzFU"/>
	</div> -->
</div>

<style lang="scss" scoped>
	#player_container {
		position: fixed;
		inset:0;
		z-index: -2;
		// filter: blur(64px);
		// opacity: 0.2;
		pointer-events: none;
	}
	.text-container {
		position: relative;
		pointer-events: none;
	}
	.text-main {
	}
	.text-radient {
		position: absolute;
		inset: 0;
		filter: blur(3rem) brightness(0.5) saturate(2.5);
		z-index: -1;
		animation: lightPulse 5s infinite ease-in-out;
		transform: scale(1);

		@keyframes lightPulse {
			0% {
				opacity: 1;
				transform: scale(1);
			}
			50% {
				opacity: 0.7;
				transform: scale(1.02);
			}
			100% {
				opacity: 1;
				transform: scale(1);
			}
		}
	}
	.placeholder-main {
		background-color: #030303;
		background-size: contain;
		background-repeat: no-repeat;
		background-position: center;
		position: fixed;
		inset: 0;
		display: grid;
		place-items: center;
		// filter: drop-shadow(0 2rem 0.75rem rgb(126, 126, 255));
		// animation: shadowMove 5s infinite ease-in-out;
		// animation: backgroundSlowPulse 15s infinite ease-in-out;

		@keyframes backgroundSlowPulse {
			0% {
				background-size: 50% 100% cover;
			}
			50% {
				background-size: 50% 50% cover;
			}
			100% {
				background-size: 50% 100% cover;
			}
		}

		@keyframes shadowMove {
			0% {
				filter: drop-shadow(2rem 2rem 0.75rem rgb(126, 126, 255));
			}
			50% {
				filter: drop-shadow(-2rem 4rem 0.75rem purple);
			}
			100% {
				filter: drop-shadow(2rem 2rem 0.75rem rgb(126, 126, 255));
			}
		}
	}
</style>
