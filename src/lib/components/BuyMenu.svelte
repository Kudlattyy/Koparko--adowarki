<script lang="ts">
	import { fly } from 'svelte/transition';
	import { T } from '@threlte/core';

	let iloscGodzin: number = 0;
	let odleglosc: number = 0;
	let pracownikDodatkowy: boolean = false;
	let liczbaRazyKorzystal: number = 0; // Dodaj pole liczbaRazyKorzystal
	let cena: number;
	let imie: string = '';
	let nazwisko: string = '';
	let email: string = '';

	async function submitForm() {
		const url = 'http://localhost/kopary-backend/index.php';
		const data = {
			iloscGodzin,
			odleglosc,
			pracownikDodatkowy,
			liczbaRazyKorzystal,
			imie,
			nazwisko,
			email // Dodaj pole liczbaRazyKorzystal
		};

		try {
			const response = await fetch(url, {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: JSON.stringify(data)
			});

			if (response.ok) {
				const responseText = await response.text();
				console.log(responseText);

				const result = JSON.parse(responseText);
				console.log(result);

				cena = result.koszt;
			} else {
				console.error('Błąd HTTP:', response.status, response.statusText);
			}
		} catch (error) {
			console.error('Błąd sieci:', error);
		}
	}

	function komunikat() {
		alert('Dziękujemy za zakup, kwota do zapłaty została wysłana na E-maila');
	}
</script>

<div class="OffMenu" transition:fly={{ delay: 500, duration: 500 }}>
	<div class="BuyMenu">
		<div class="dmodel" />
		<div class="InputMenu">
			<form on:submit|preventDefault={submitForm}>
				<label for="iloscGodzin">Ilość godzin wynajmu:</label>
				<input
					class="input input-bordered input-warning w-full max-w-xs"
					type="number"
					id="iloscGodzin"
					bind:value={iloscGodzin}
				/>
				<br />

				<label for="odleglosc">Odległość od klienta (km):</label>
				<input
					class="input input-bordered input-warning w-full max-w-xs"
					type="number"
					id="odleglosc"
					bind:value={odleglosc}
				/>
				<br />

				<label for="pracownikDodatkowy">Czy potrzebny pracownik dodatkowy:</label>
				<br />
				<input
					class="checkbox checkbox-warning"
					type="checkbox"
					id="pracownikDodatkowy"
					bind:checked={pracownikDodatkowy}
				/>
				<br />

				<label for="liczbaRazyKorzystal">Liczba razy korzystał z usługi:</label>
				<input
					class="input input-bordered input-warning w-full max-w-xs"
					type="number"
					id="liczbaRazyKorzystal"
					bind:value={liczbaRazyKorzystal}
				/>
				<br />

				<label for="imie">Imię:</label>
				<br />
				<input
					class="input input-bordered input-warning w-full max-w-xs"
					type="text"
					id="imie"
					bind:value={imie}
				/>
				<br />

				<label for="nazwisko">Nazwisko:</label>
				<br />
				<input
					class="input input-bordered input-warning w-full max-w-xs"
					type="text"
					id="nazwisko"
					bind:value={nazwisko}
				/>
				<br />

				<label for="email">E-mail:</label>
				<br />
				<input
					class="input input-bordered input-warning w-full max-w-xs"
					type="email"
					id="email"
					bind:value={email}
				/>
				<br />

				<button on:click={komunikat} class="btn btn-warning mt-20 btn-lg" type="submit"
					>Oblicz koszt i wyślij wycenę</button
				>
			</form>
			{#if cena !== undefined}
				<p>Cena: {cena} zł</p>
			{/if}
		</div>
	</div>
</div>

<style lang="scss">
	.OffMenu {
		width: 100vw;
		height: 100vh;
		background-color: rgba(82, 82, 82, 0.318);
		z-index: 10;
		position: absolute;
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
				height: 100vh;
			}
			.InputMenu {
				width: 25vw;
				height: 75vh;
				background-color: rgba(28, 28, 28, 0.9);

				box-shadow: 3px 3px 3px 3px rgba(255, 194, 61, 0.3);
				border-radius: 10px;
				backdrop-filter: blur(15px);
				text-align: center;
				padding: 30px;
				margin: 50px;
			}
		}
	}
</style>
