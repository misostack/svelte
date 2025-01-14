<script lang="ts">
	import '../app.css';
	import environment from '../shared/environment';
	let { children } = $props();
	const {APP_NAME, APP_VERSION} = environment;
</script>
<header>
	<h1>{APP_NAME}</h1>
</header>
<main>
{@render children()}
</main>
<footer>
	<p>Made with love by misostack. Power by svelte 5. Version: {APP_VERSION}</p>
</footer>
