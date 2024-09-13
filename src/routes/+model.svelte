<script>
    import { onMount } from 'svelte';
    import * as tf from '@tensorflow/tfjs';

    let model;
    let isLoading;
    let error = null;

    export const loadModel = async () => {
        try {
            // model = await tf.loadGraphModel()
            isLoading = false;
        } catch (e) {
            error = e;
            isLoading = false;
        }
    };

    onMount(loadModel);
</script>