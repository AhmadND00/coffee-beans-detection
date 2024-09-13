<script lang = "ts">
    import * as tf from '@tensorflow/tfjs';
</script>
<!-- 
const loadModel = async () => {
    const version = 2;
    const alpha = 0.5;
    model = await
} -->

<input type='file' on:change={handleImageUpload} accept='image/*' />
{#if imageUrl}
    <img src={imageUrl} alt="Uploaded Image" />
    <button on:click={runInference}>Run Detection</button>
{/if}

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
