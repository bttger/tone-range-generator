<script lang="ts">
    import {AutoFilter, Noise, Oscillator} from 'tone'

    let from = 50;
    let to = 8000;
    let seconds = 15;

    let runningTimeout;
    let oscillator: Oscillator;

    function start() {
        runningTimeout = setTimeout(() => {
            oscillator.stop();
            runningTimeout = undefined;
        }, seconds * 1000);

        oscillator = new Oscillator({
            type: "sine",
            frequency: from,
            detune: 0,
            phase: 0,
            partialCount: 0,
            volume: -16,
        }).toDestination().start();
        oscillator.frequency.exponentialRampTo(to, seconds)
    }

    function stop() {
        oscillator.stop();
        clearTimeout(runningTimeout);
        runningTimeout = undefined;
    }

    // Pink Noise
    let playingPinkNoise = false;
    let noise: Noise;

    function startPinkNoise() {
        playingPinkNoise = true;
        noise = new Noise('pink');
        const filter = new AutoFilter({
            baseFrequency: 200,
            octaves: 8
        }).toDestination();
        noise.connect(filter).start();
    }

    function stopPinkNoise() {
        noise.stop();
        playingPinkNoise = false;
    }
</script>

<main>
    <h1>Generate a tone range to tune your speakers/equalizer</h1>

    <h2>
        ATTENTION: Turn down the volume before you run the script! The oscillator can cause permanent
        hearing damage. Use at your own risk.
    </h2>

    <div>
        <label>From (Hz)</label>
        <input type=number min=10 max=20000 bind:value={from}>
    </div>

    <div>
        <label>To (Hz)</label>
        <input type=number min=10 max=20000 bind:value={to}>
    </div>

    <div>
        <label>Duration (Seconds)</label>
        <input type=number min=2 max=120 bind:value={seconds}>
    </div>

    {#if runningTimeout}
        <button on:click={stop}>Stop</button>
    {:else}
        <button on:click={start}>Start</button>
    {/if}

    <h2>
        Pink Noise
    </h2>
    {#if playingPinkNoise}
        <button on:click={stopPinkNoise}>Stop</button>
    {:else}
        <button on:click={startPinkNoise}>Start</button>
    {/if}
</main>

<style>

</style>
