# Tone Range Generator

The tool generates a sine wave tone which automatically increases exponentially until the user defined range has been run through. Just set the `start` and `end` frequency in hz, the `duration` in seconds, and hit `start`.

Yes, the app looks like crap, but that's intended - it does its job.

## Tuning your speakers / equalizer

In my case, I have used the free Android app [Spectroid](https://play.google.com/store/apps/details?id=org.intoorbit.spectrum), but you can use any other sound spectrum analyzer app that offers a line that holds the maximum recorded sound pressure level (dB). The goal is, at least in my opinion, to get the "max hold" line as flat as possible.

The process is that you hold your smartphone at the position where your head is usually, and then you press `start` to  run through the frequencies and record it with your spectrum analyzer app. Before each optimization run you should reset your "max hold" line. The line will show you which frequencies are under- and overrepresented. You should then try to optimize the sound with the position of your speakers, your room layout, an equalizer, and your speakers internal options.

## Development

### Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Svelte](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode).

