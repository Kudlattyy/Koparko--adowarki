<script lang="ts">
	import BuyMenu from '$lib/components/BuyMenu.svelte';

	let boolean = false;
	function OpenBuyMenu() {
		boolean = true;
	}

	type oferta = {
		src: string;
		model: string;
		spec: string[];
	};

	let oferty: oferta[] = [
		{
			src: '/428.png',
			model: '428',
			spec: [
				'Moc użyteczna: 52kW',
				'Masa Eksplotacyjna-Znamowiona:8270kg',
				'Masa Eksploatacyjna — Maksymalnie:11000kg'
			]
		},
		{
			src: '/432.png',
			model: '432',
			spec: [
				'Moc użyteczna: 68kW',
				'Masa Eksplotacyjna-Znamowiona:8469kg',
				'Masa Eksploatacyjna — Maksymalnie:11000kg'
			]
		},
		{
			src: '/434.png',
			model: '434',
			spec: [
				'Moc użyteczna: 68kW',
				'Masa Eksplotacyjna-Znamowiona:9170 kg',
				'Masa Eksploatacyjna — Maksymalnie:11500kg'
			]
		}
	];
</script>

{#if boolean}
	<BuyMenu />
{/if}

<div class="scroll">
	<section class="slide slide--first">
		<div class="first-section-left">
			<div class="text-2xl">
				<h1 class="text-8xl text-amber-400">Cat</h1>
				<br />
				Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
				labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
				nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
				velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
				sunt in culpa qui officia deserunt mollit anim id est laborum.
			</div>
		</div>
		<div class="first-section-right"><img src="/kopara.png" alt="placeholder" /></div>
	</section>

	<section class="slide slide--second">
		<div class="slide slide--second-main">
			<div class="slide slide--second-left">Filtry</div>
			<div class="slide slide--second-right">
				{#each oferty as oferta}
					<div class="card w-96 bg-base-100 shadow-xl">
						<figure>
							<img src={oferta.src} alt="Shoes" />
						</figure>
						<div class="card-body">
							<h2 class="card-title">{oferta.model}</h2>
							{#each oferta.spec as index}<p>
									{index}
								</p>{/each}

							<div class="card-actions justify-end">
								<button class="btn btn-primary" on:click={OpenBuyMenu}>Buy Now</button>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>
</div>

<style lang="scss">
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
			align-items: center;
			padding-left: 100px;
			width: 50%;
			margin-left: 10px;
		}
		.first-section-right {
			display: flex;
		}
	}
	.slide--second {
		background-color: #1f1c1c;
		display: grid;
		place-items: center;
		.slide--second-main {
			height: 80vh;
			width: 90vw;
			background-color: #333333;
			border-radius: 10px;
			border: #ffc23d9d 2px solid;
			box-shadow: 3px 3px 3px 3px rgba(255, 194, 61, 0.3);
			display: flex;
			.slide--second-left {
				height: 76vh;
				width: 15vw;
				margin-top: 20px;
				margin-left: 20px;
				background: rgba(27, 27, 27, 0.4);
				border-radius: 10px;
				border: #ffc23d9d 1px solid;
			}
			.slide--second-right {
				height: 76vh;
				width: 71.7vw;
				background: rgba(27, 27, 27, 0.4);
				margin-top: 20px;
				margin-left: 20px;
				border-radius: 10px;
				border: #ffc23d9d 1px solid;
				display: grid;
				grid-template-columns: 33% 33% 33%;
				column-gap: 20px;
				padding: 25px;
			}
		}
	}
	
</style>
