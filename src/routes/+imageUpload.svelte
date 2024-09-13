<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();
    let imageUrl = '';

    function handleImageUpload(event) {
        const file = event.target.files[0];
        imageUrl = URL.createObjectURL(file);
        dispatch('imageUploaded', { imageUrl} );
    };
</script>

<input type="file" on:change={handleImageUpload} accept="image/*" />
{#if imageUrl}
    <img src={imageUrl} alt="Uploaded Image" />
{/if}