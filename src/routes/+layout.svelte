<script lang="ts">
	import '$lib/styles/body.scss';
</script>

<nav class="navbar">
	<div class="nav-logo"><img class="cat" src="/CAT-logo.png" alt="placeholder" /></div>
</nav>

<slot />

<style lang="scss">
	.navbar {
		position: fixed;
		top: 0%;
		height: 8vh;
		width: 100vw;
		background-color: #ffc13d;
		z-index: 10;
		.nav-logo {
			display: grid;
			place-items: center;
			height: 8vh;
			.cat {
				width: 10vw;
				height: 5vh;
			}
		}
	}
</style>
