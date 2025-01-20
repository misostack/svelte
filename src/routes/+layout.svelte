<script lang="ts">
    
    import '../app.css';
    import environment from '../shared/environment';
    let { children } = $props();
    const { APP_NAME, APP_VERSION } = environment;

</script>

<div>
    <header>
        <h1>{APP_NAME}</h1>
    </header>
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/runes">Runes Example</a></li>        
    </ul>

    <main>
        {@render children()}
    </main>

    <footer class="text-center mt-4 p-4">
        <p>Made with love by misostack. Powered by Svelte 5. Version: {APP_VERSION}</p>
    </footer>
</div>

<style>

</style>