<script>
    import * as tf from '@tensorflow/tfjs';

    export let model;
    export let imageUrl;
    let results = [];

    async function runDetection() {
        const img = await tf.browser.fromPixels(document.querySelector('img'));
        const resized = tf.image.resizeBilinear(img, [640, 640]);
        const expanded = resized.expandDims(0);
        const normalized = expanded.div(255.0);
        
        const prediction = await model.executeAysnc(normalized);

        results = await postProcessResults(prediction);

        tf.dispose([img, resized, expanded, normalized, ... predictions])

    }

async function postProcessResults(predictions) {
    
}
</script>

