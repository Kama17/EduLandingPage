<script lang="ts">
	import Header from './Header.svelte';
	import Footer from './Footer.svelte';
	import 'animate.css';
	import '../app.css';

	let { children } = $props();

</script>

<div class="app flex flex-col min-h-screen">
	<Header/>

	<main>
		{@render children()}
	</main>

</div>

<Footer/>

