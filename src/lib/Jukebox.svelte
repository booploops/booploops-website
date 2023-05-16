<script>
	let bigMode = false;

	function toggleBigMode() {
		bigMode = !bigMode;
	}
</script>

<div class="jukebox" class:bigmode={bigMode}>
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<div class="jukebox-metadata" on:click={toggleBigMode}>
		<div class="song-name">Song Name</div>
		<div class="artist-name">Artist Name</div>
	</div>
</div>

<style lang="scss">
	.jukebox {
		background: rgb(255 255 255 / 5%);
		border-radius: 16px 16px 0 0;
		height: 80px;
		position: absolute;
		bottom: 0px;
		left: 0px;
		right: 0px;
		box-shadow: inset 0px 1.5px 0px 0.1px rgb(255 255 255 / 15%);
		transition: height .3s cubic-bezier(.47,1.64,.41,.8);
		backdrop-filter: blur(120px) saturate(280%) contrast(1.1) brightness(0.6);

		&.bigmode {
			height: 80vh;
		}
	}

	.jukebox-metadata {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 80px;
		cursor: pointer;

		.song-name {
			font-size: 1.5rem;
		}
		.artist-name {
			font-size: 1rem;
			opacity: 0.7;
		}
	}
</style>
