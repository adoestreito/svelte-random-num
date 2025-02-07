<script lang="ts">
	import '../app.css';
	let { children } = $props();
	import { injectAnalytics } from '@vercel/analytics/sveltekit';
	import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';

	injectAnalytics();
	injectSpeedInsights();
</script>

{@render children()}
