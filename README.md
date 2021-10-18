# Tone Range Generator

## Features

- Sine wave tone generation for a specified range (with a definable duration)
- Pink noise generation (20 Hz - 20 kHz)
- Crappy look - but hey, it does its job

## Tuning your speakers / equalizer

In my case, I have used the free Android app [Spectroid](https://play.google.com/store/apps/details?id=org.intoorbit.spectrum), but you can use any other sound spectrum analyzer app that offers a line that holds the maximum recorded sound pressure level (dB). The goal is, at least in my opinion, to get the "max hold" line as flat as possible.

The process is that you hold your smartphone at the position where your head is usually, and then you press `start` to  run through the frequencies (or to play the pink noise) and record it with your spectrum analyzer app. Before each optimization run you should reset your "max hold" line. The line will show you which frequencies are under- or overrepresented. You should then try to optimize the sound with the position of your speakers, your room layout, an equalizer, and your speakers internal options.

> Tip: When using an equalizer, it is better to decrease the level of frequencies rather than boosting them. It is less likely to have distortion.

The following image shows the red "max hold" line. On the top right you can reset it.

<img src="https://i.imgur.com/UeZy1M7.jpeg" width="380" title="Tone Range Generation: Screenshot of the Spectroid app" alt="Tone Range Generation: Screenshot of the Spectroid app">

<img src="https://i.imgur.com/DJfLSmp.jpg" width="380" title="Pink Noise: Screenshot of the Spectroid app" alt="Pink Noise: Screenshot of the Spectroid app">

## Development

### Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Svelte](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode).

### Run the development server

```bash
npm run dev
```
