<script lang="ts">
	import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';
	import '../app.css';
	import Navbar from '$lib/components/navbar.svelte';
  	import Footer from '$lib/components/footer.svelte';
	
		injectSpeedInsights();
	</script>

	<Navbar />
	<main class="min-h-screen">
		<slot />
	</main>
	<Footer />