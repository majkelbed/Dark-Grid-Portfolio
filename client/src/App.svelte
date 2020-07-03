<script>
	import Sidebar from './components/Sidebar.svelte';
	import MainFeed from './components/MainFeed.svelte';
</script>

<div class="page-container">
	<Sidebar></Sidebar>
	<MainFeed></MainFeed>
</div>

<style>
	.page-container {
		display: grid;
		grid-template-columns: minmax(300px, 1fr) 1fr;

		overflow:auto;

		width: 100vw;
		max-width:100%;
		height: 100%;

		padding: 3rem;
		
		color:white;
	}

	@media screen and (max-width: 900px) {
		.page-container {
			grid-template-columns: 1fr;
		}
	}

	@media screen and (min-width: 1400px) {
		.page-container {
			max-width: 1360px;
			margin: 0 auto;
		}
	}
	
</style>