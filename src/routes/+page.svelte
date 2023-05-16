<script>
	import BooploopsText from '$lib/BooploopsText.svelte';
	import Jukebox from '$lib/Jukebox.svelte';
	import Player from '$lib/Player.svelte';
	import ScanlineOverlay from '$lib/ScanlineOverlay.svelte';
</script>

<svelte:head>
	<title>booploops</title>
	<meta name="description" content="booploops website" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
	<meta name="theme-color" content="#000000" />
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
	<ScanlineOverlay></ScanlineOverlay>
</div>

<style lang="scss" scoped>
	#player_container {
		position: fixed;
		inset: 0;
		z-index: -2;
		// filter: blur(64px);
		// opacity: 0.2;
		pointer-events: none;
	}
	.text-container {
		position: relative;
		pointer-events: none;
		animation: textFadeIn 2s ease-in-out;

		@keyframes textFadeIn {
			0% {
				transform: translateY(-10vh);
				opacity:0;
			}
			100% {
				transform: translateY(0px);
				opacity:1;
			}
		}
	}
	.text-main {
	}
	.text-radient {
		position: absolute;
		inset: 0;
		filter: blur(3rem) brightness(1) saturate(2.5);
		z-index: -1;
		animation: lightPulse 5s infinite ease-in-out;
		transform: scale(1);

		@keyframes lightPulse {
			0% {
				opacity: .8;
				transform: scale(1) skew(10deg);
			}
			50% {
				opacity: 0.9;
				transform: scale(1.02) skew(-10deg);
			}
			100% {
				opacity: .8;
				transform: scale(1) skew(10deg);
			}
		}
	}
	.placeholder-main {
		background-color: #000;
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
