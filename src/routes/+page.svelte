<script lang="ts">
	import '$lib/styles/body.scss';
</script>

<body>
	<nav class="navbar">
		<div class="nav-logo"><img class="cat" src="/CAT-logo.png" alt="placeholder" /></div>
	</nav>

	<div class="panel-main">
		<div class="panel-main-left">
			<h1>Lorem ipsum dolor sit amet</h1>
			consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
			Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
			consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat
			nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt
			mollit anim id est laborum
		</div>
		<div class="panel-main-right"><img src="/kopara.png" alt="" /></div>
	</div>
</body>

<style lang="scss">
	.navbar {
		position: fixed;
		top: 0%;
		height: 8vh;
		width: 100vw;
		background-color: #2d1d09;
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

	.panel-main {
		display: flex;
		height: 80vh;
		width: 100vw;
		.panel-main-left {
			width: 50vw;
			display: flex;
			place-items: center;
		}
		.panel-main-right {
			width: 50vw;
		}
	}
</style>
