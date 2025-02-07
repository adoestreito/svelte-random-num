<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { injectAnalytics } from '@vercel/analytics/sveltekit';
</script>

{@render children()}
