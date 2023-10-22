<script lang="ts">
	import { fly } from 'svelte/transition';
</script>

<div class="OffMenu" transition:fly={{ delay: 500, duration: 500 }}>
	<div class="BuyMenu">
		<div class="dmodel" />
		<div class="InputMenu">
			<form id="calculator-form">
				<label for="hours">Ilość godzin wynajmu:</label>
				<input type="number" id="hours" required />
				<br /> <br />
				<label for="distance">Odległość od klienta (km):</label>
				<input type="number" id="distance" required />
				<br /> <br />
				<label for="additionalWorker">Czy potrzebny pracownik dodatkowy?</label>
				<input type="radio" id="additionalWorker" />
				<br /> <br />
				<label for="promotion">Czy masz rabat?</label>
				<input type="radio" id="promotion" />
				<br /> <br />
				<button type="submit">Oblicz koszt</button>
			</form>
			<br />
			<div id="result" />
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
