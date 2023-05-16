<div class="boop-text">booploops</div>

<style lang="scss">
	.boop-text {
		font-size: clamp(16vw, 4vw, 22px);
        font-weight: 800;
		text-align: center;
		background: -webkit-linear-gradient(rgb(126, 126, 255), purple);
        background-size: 100% 100%;
        background-position: 0% 50%;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
        animation: bgSize 8s infinite ease-in-out;
        transform: rotate(0deg);
        user-select: none;

        @keyframes bgSize {
            0% {
                transform: rotate(20deg);
                background-size: 100% 100%;
            }
            50% {
                transform: rotate(-20deg);
                background-size: 100% 10%;
            }
            100% {
                transform: rotate(20deg);
                background-size: 100% 100%;
            }
        }
	}
</style>
