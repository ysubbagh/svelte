<script lang="ts">
	import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';
	import '../app.css';
	import Navbar from '$lib/components/navbar.svelte';
  	import Footer from '$lib/components/footer.svelte';
	
	let { children } = $props();
	injectSpeedInsights();
	
</script>

<Navbar />
<main class="min-h-screen">
  {@render children()} <!-- page content here -->
</main>
<Footer />