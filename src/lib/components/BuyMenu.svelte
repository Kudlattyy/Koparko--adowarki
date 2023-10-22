<script lang="ts">
	import { fly } from 'svelte/transition';

	const priceForHour = 200;
	const priceForDistance = 10;
	const priceForWorkerHour = 30;
	let hours: number;
	let distance: number;
	let promotion: number;
	let additionalWorker: boolean;
	let cost = 0;
	const CalculatePrice = () => {
		cost = 0;
		cost += hours * priceForHour;
		cost += distance * priceForDistance;
		if (additionalWorker) cost += hours * priceForWorkerHour;
		if (promotion > 2) {
			cost -= cost * (0.1 * hours);
		}
	};
</script>

<div class="OffMenu" transition:fly={{ delay: 500, duration: 500 }}>
	<div class="BuyMenu">
		<div class="dmodel" />
		<div class="InputMenu">
			<form id="calculator-form">
				<label for="hours">Ilość godzin wynajmu:</label>
				<input type="number" id="hours" required bind:value={hours} />
				<br /> <br />
				<label for="distance">Odległość od klienta (km):</label>
				<input type="number" id="distance" required bind:value={distance} />
				<br /> <br />
				<label for="additionalWorker">Czy potrzebny pracownik dodatkowy?</label>
				<input type="radio" id="additionalWorker" bind:value={additionalWorker} />
				<br /> <br />
				<label for="promotion">Ile razy używałeś usług firmy?</label>
				<input type="number" id="promotion" bind:value={promotion} />
				<br /> <br />
				<button on:click={CalculatePrice}>Oblicz koszt</button>
			</form>
			<br />
			<div id="result">{cost}</div>
		</div>
	</div>
</div>

<style lang="scss">
	.OffMenu {
		width: 100vw;
		height: 100vh;
		background-color: rgba(82, 82, 82, 0.318);
		position: absolute;
		z-index: 10;
		display: grid;
		place-items: center;
		.BuyMenu {
			width: 100vw;
			height: 100vh;
			background-color: rgba(28, 28, 28, 0.9);
			backdrop-filter: blur(15px);
			display: flex;
			.dmodel {
				width: 70vw;
				height: 100vw;
			}
			.InputMenu {
				width: 30vw;
				text-align: center;
				padding: 30px;
			}
		}
	}
</style>
