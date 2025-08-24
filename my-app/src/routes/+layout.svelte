<script lang="ts">
	import '../app.css';
	import Navbar from '$lib/components/navbar.svelte';
  	import Footer from '$lib/components/footer.svelte';
	
	let { children } = $props();
</script>

<Navbar />
<main class="min-h-screen">
  {@render children()} <!-- page content here -->
</main>
<Footer />