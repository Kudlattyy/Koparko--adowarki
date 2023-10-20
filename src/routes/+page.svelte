<div class="scroll">
	<section class="slide slide--first">
		<div class="first-section-left">
			<div class="AboutUs">
				<h1>Cat</h1>
				<br />
				Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
				labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
				nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
				velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
				sunt in culpa qui officia deserunt mollit anim id est laborum.
			</div>
		</div>
		<div class="first-section-right"><img class="Kopara" src="/kopara.png" alt="" /></div>
	</section>

	<section class="slide slide--second">
		<div class="slide slide--second-main" />
	</section>
</div>

<style lang="scss">
	h1 {
		font-size: 92px;
		color: #ffc13d;
	}

	.scroll {
		height: 100%;
		width: 100%;
		scroll-snap-type: y mandatory;
		overflow: scroll;
		scroll-padding-top: 8vh;
	}

	.slide {
		height: 100vh;
		width: 100vw;
		scroll-snap-align: center;
	}

	.slide--first {
		background-color: #1f1c1c;
		display: flex;
		.first-section-left {
			display: flex;
			justify-content: center;
			padding-top: 200px;
			width: 50%;
			margin-left: 10px;
			.AboutUs {
				color: whitesmoke;
				font-size: 18px;
			}
		}
		.Kopara {
			height: 100%;
		}
	}
	.slide--second {
		background-color: #1f1c1c;
		display: grid;
		place-items: center;
		.slide--second-main {
			height: 70vh;
			width: 60vw;
			background-color: #333333;
			border-radius: 10px;
			border: #ffc23d9d 2px solid;
			box-shadow: 3px 3px 3px 3px rgba(255, 194, 61, 0.3);
		}
	}
</style>
